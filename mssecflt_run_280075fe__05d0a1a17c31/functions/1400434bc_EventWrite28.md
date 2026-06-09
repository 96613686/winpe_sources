# EventWrite28

- ea: `0x1400434bc`
- end: `0x14004377a`
- name: `EventWrite28`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140040f3c`

## callees

- `0x140008714`
- `0x14000876c`
- `0x140009b80`
- `0x140011650`
- `0x1400434bc`
- `0x140043e18`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140043722`
- `ntoskrnl!EtwWrite` at `0x140043722`

## pseudocode

```c
__int64 __fastcall EventWrite28(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        char a5,
        __int64 a6,
        int a7,
        unsigned __int64 a8,
        __int64 a9)
{
  unsigned int v9; // esi
  struct _SLIST_ENTRY *v10; // r14
  struct _SLIST_ENTRY *v11; // rdi
  PSLIST_ENTRY EtwDescriptorBuffer; // rax
  PSLIST_ENTRY UserData; // rbx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // esi
  struct _SLIST_ENTRY *v21; // [rsp+30h] [rbp-30h] BYREF
  struct _SLIST_ENTRY *v22; // [rsp+38h] [rbp-28h] BYREF
  int v23; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+A0h] [rbp+40h] BYREF
  int v27; // [rsp+A8h] [rbp+48h] BYREF
  int v28; // [rsp+B0h] [rbp+50h] BYREF
  int v29; // [rsp+B8h] [rbp+58h] BYREF

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v26 = a1;
  v25 = a9;
  v9 = 1024;
  v23 = 0;
  v10 = 0;
  v24 = 0;
  v11 = 0;
  v22 = 0;
  v21 = 0;
  EtwDescriptorBuffer = SecGetEtwDescriptorBuffer(0xDu);
  UserData = EtwDescriptorBuffer;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  v15 = a6;
  EtwDescriptorBuffer->Next = (struct _SLIST_ENTRY *)&v26;
  EtwDescriptorBuffer[1].Next = (struct _SLIST_ENTRY *)&v29;
  EtwDescriptorBuffer[2].Next = (struct _SLIST_ENTRY *)&a5;
  EtwDescriptorBuffer[3].Next = (struct _SLIST_ENTRY *)&v27;
  EtwDescriptorBuffer[4].Next = (struct _SLIST_ENTRY *)&v28;
  EtwDescriptorBuffer[5].Next = (struct _SLIST_ENTRY *)&a8;
  EtwDescriptorBuffer[6].Next = (struct _SLIST_ENTRY *)&v25;
  EtwDescriptorBuffer[7].Next = (struct _SLIST_ENTRY *)&a7;
  *((_QWORD *)&EtwDescriptorBuffer->Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[1].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[2].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[3].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[4].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[5].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[6].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[7].Next + 1) = 4;
  *((_DWORD *)&EtwDescriptorBuffer[8].Next + 2) = a7;
  EtwDescriptorBuffer[9].Next = (struct _SLIST_ENTRY *)&v23;
  EtwDescriptorBuffer[11].Next = (struct _SLIST_ENTRY *)&v24;
  EtwDescriptorBuffer[8].Next = (struct _SLIST_ENTRY *)v15;
  *((_DWORD *)&EtwDescriptorBuffer[8].Next + 3) = 0;
  *((_QWORD *)&EtwDescriptorBuffer[9].Next + 1) = 4;
  EtwDescriptorBuffer[10].Next = 0;
  *((_QWORD *)&EtwDescriptorBuffer[10].Next + 1) = 0;
  *((_QWORD *)&EtwDescriptorBuffer[11].Next + 1) = 4;
  EtwDescriptorBuffer[12].Next = 0;
  *((_QWORD *)&EtwDescriptorBuffer[12].Next + 1) = 0;
  if ( _bittest64((const signed __int64 *)&xmmword_14001B740, 0x2Fu) )
  {
    v16 = SafeCopyMemory(v25, 4096, &v22, &v23);
    v10 = v22;
    if ( v16 >= 0 )
    {
      *((_QWORD *)&UserData[9].Next + 1) = 4;
      UserData[9].Next = (struct _SLIST_ENTRY *)&v23;
      v17 = v23;
      if ( v23 )
      {
        UserData[10].Next = v10;
        *((_DWORD *)&UserData[10].Next + 2) = v17;
        *((_DWORD *)&UserData[10].Next + 3) = 0;
      }
    }
    while ( a8 >= v9 )
    {
      v18 = SafeCopyMemory(a8 - v9, v9, &v21, &v24);
      if ( v18 >= 0 && v9 == v24 )
        goto LABEL_15;
      v9 >>= 1;
      if ( !v9 )
      {
        if ( v18 < 0 )
          break;
LABEL_15:
        *((_QWORD *)&UserData[11].Next + 1) = 4;
        UserData[11].Next = (struct _SLIST_ENTRY *)&v24;
        if ( v23 )
        {
          v19 = v24;
          v11 = v21;
          UserData[12].Next = v21;
          *((_QWORD *)&UserData[12].Next + 1) = v19;
          goto LABEL_18;
        }
        break;
      }
    }
    v11 = v21;
  }
  else if ( v15 && a7 )
  {
    a7 = 280;
    EtwDescriptorBuffer[8].Next = (struct _SLIST_ENTRY *)v15;
    *((_QWORD *)&EtwDescriptorBuffer[8].Next + 1) = 280;
  }
LABEL_18:
  v20 = EtwWrite(Microsoft_Windows_SECHandle, &Event28, 0, 0xDu, (PEVENT_DATA_DESCRIPTOR)UserData);
  if ( v10 )
    SecFreePool(v10, 0x64446353u);
  if ( v11 )
    SecFreePool(v11, 0x64446353u);
  SecReleaseEtwDescriptorBuffer(UserData);
  return v20;
}

```

## disassembly

```asm
0x1400434bc  mov     rax, rsp
0x1400434bf  mov     [rax+20h], r9d
0x1400434c3  mov     [rax+18h], r8d
0x1400434c7  mov     [rax+10h], edx
0x1400434ca  mov     [rax+8], rcx
0x1400434ce  push    rbp
0x1400434cf  push    rbx
0x1400434d0  push    rsi
0x1400434d1  push    rdi
0x1400434d2  push    r13
0x1400434d4  push    r14
0x1400434d6  push    r15
0x1400434d8  mov     rbp, rsp
0x1400434db  sub     rsp, 60h
0x1400434df  mov     rax, cs:__security_cookie
0x1400434e6  xor     rax, rsp
0x1400434e9  mov     [rbp+var_10], rax
0x1400434ed  mov     rax, [rbp+arg_40]
0x1400434f4  xor     r15d, r15d
0x1400434f7  mov     [rbp+var_18], rax
0x1400434fb  mov     esi, 400h
0x140043500  mov     [rbp+var_20], r15d
0x140043504  mov     r14d, r15d
0x140043507  mov     [rbp+var_1C], r15d
0x14004350b  mov     edi, r15d
0x14004350e  lea     ecx, [r15+0Dh]
0x140043512  mov     [rbp+var_28], r15
0x140043516  mov     [rbp+var_30], r15
0x14004351a  call    SecGetEtwDescriptorBuffer
0x14004351f  mov     rbx, rax
0x140043522  test    rax, rax
0x140043525  jnz     short loc_140043531
0x140043527  mov     eax, 0C000009Ah
0x14004352c  jmp     loc_14004375E
0x140043531  mov     rcx, [rbp+arg_28]
0x140043535  lea     rax, [rbp+arg_0]
0x140043539  mov     [rbx], rax
0x14004353c  lea     rax, [rbp+arg_18]
0x140043540  mov     [rbx+10h], rax
0x140043544  lea     rax, [rbp+arg_20]
0x140043548  mov     [rbx+20h], rax
0x14004354c  lea     rax, [rbp+arg_8]
0x140043550  mov     [rbx+30h], rax
0x140043554  lea     rax, [rbp+arg_10]
0x140043558  mov     [rbx+40h], rax
0x14004355c  lea     rax, [rbp+arg_38]
0x140043560  mov     [rbx+50h], rax
0x140043564  lea     rax, [rbp+var_18]
0x140043568  mov     [rbx+60h], rax
0x14004356c  lea     rax, [rbp+arg_30]
0x140043570  mov     [rbx+70h], rax
0x140043574  mov     qword ptr [rbx+8], 8
0x14004357c  mov     qword ptr [rbx+18h], 4
0x140043584  mov     qword ptr [rbx+28h], 8
0x14004358c  mov     qword ptr [rbx+38h], 4
0x140043594  mov     qword ptr [rbx+48h], 4
0x14004359c  mov     qword ptr [rbx+58h], 8
0x1400435a4  mov     qword ptr [rbx+68h], 8
0x1400435ac  mov     qword ptr [rbx+78h], 4
0x1400435b4  mov     eax, [rbp+arg_30]
0x1400435b7  mov     [rbx+88h], eax
0x1400435bd  lea     rax, [rbp+var_20]
0x1400435c1  mov     [rbx+90h], rax
0x1400435c8  lea     rax, [rbp+var_1C]
0x1400435cc  mov     [rbx+0B0h], rax
0x1400435d3  mov     [rbx+80h], rcx
0x1400435da  mov     [rbx+8Ch], r15d
0x1400435e1  mov     qword ptr [rbx+98h], 4
0x1400435ec  mov     [rbx+0A0h], r15
0x1400435f3  mov     [rbx+0A8h], r15
0x1400435fa  mov     qword ptr [rbx+0B8h], 4
0x140043605  mov     [rbx+0C0h], r15
0x14004360c  mov     [rbx+0C8h], r15
0x140043613  bt      qword ptr cs:xmmword_14001B740, 2Fh ; '/'
0x14004361c  jb      short loc_14004364C
0x14004361e  test    rcx, rcx
0x140043621  jz      loc_140043706
0x140043627  cmp     [rbp+arg_30], r15d
0x14004362b  jbe     loc_140043706
0x140043631  mov     eax, 118h
0x140043636  mov     [rbp+arg_30], eax
0x140043639  mov     [rbx+80h], rcx
0x140043640  mov     [rbx+88h], rax
0x140043647  jmp     loc_140043706
0x14004364c  mov     rcx, [rbp+var_18]
0x140043650  lea     r9, [rbp+var_20]
0x140043654  lea     r8, [rbp+var_28]
0x140043658  mov     edx, 1000h
0x14004365d  call    SafeCopyMemory
0x140043662  mov     r14, [rbp+var_28]
0x140043666  test    eax, eax
0x140043668  js      short loc_14004369B
0x14004366a  lea     rax, [rbp+var_20]
0x14004366e  mov     qword ptr [rbx+98h], 4
0x140043679  mov     [rbx+90h], rax
0x140043680  mov     eax, [rbp+var_20]
0x140043683  test    eax, eax
0x140043685  jz      short loc_14004369B
0x140043687  mov     [rbx+0A0h], r14
0x14004368e  mov     [rbx+0A8h], eax
0x140043694  mov     [rbx+0ACh], r15d
0x14004369b  mov     rcx, [rbp+arg_38]
0x14004369f  mov     eax, esi
0x1400436a1  cmp     rcx, rax
0x1400436a4  jb      short loc_140043702
0x1400436a6  sub     rcx, rax
0x1400436a9  lea     r9, [rbp+var_1C]
0x1400436ad  lea     r8, [rbp+var_30]
0x1400436b1  mov     edx, esi
0x1400436b3  call    SafeCopyMemory
0x1400436b8  test    eax, eax
0x1400436ba  js      short loc_1400436C1
0x1400436bc  cmp     esi, [rbp+var_1C]
0x1400436bf  jz      short loc_1400436C9
0x1400436c1  shr     esi, 1
0x1400436c3  jnz     short loc_14004369B
0x1400436c5  test    eax, eax
0x1400436c7  js      short loc_140043702
0x1400436c9  lea     rax, [rbp+var_1C]
0x1400436cd  mov     qword ptr [rbx+0B8h], 4
0x1400436d8  mov     [rbx+0B0h], rax
0x1400436df  cmp     [rbp+var_20], r15d
0x1400436e3  jbe     short loc_140043702
0x1400436e5  mov     eax, [rbp+var_1C]
0x1400436e8  mov     rdi, [rbp+var_30]
0x1400436ec  mov     [rbx+0C0h], rdi
0x1400436f3  mov     [rbx+0C8h], eax
0x1400436f9  mov     [rbx+0CCh], r15d
0x140043700  jmp     short loc_140043706
0x140043702  mov     rdi, [rbp+var_30]
0x140043706  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14004370d  lea     rdx, Event28; EventDescriptor
0x140043714  mov     r9d, 0Dh; UserDataCount
0x14004371a  mov     [rsp+60h+UserData], rbx; UserData
0x14004371f  xor     r8d, r8d; ActivityId
0x140043722  call    cs:__imp_EtwWrite
0x140043729  nop     dword ptr [rax+rax+00h]
0x14004372e  mov     esi, eax
0x140043730  test    r14, r14
0x140043733  jz      short loc_140043742
0x140043735  mov     edx, 64446353h; Tag
0x14004373a  mov     rcx, r14; P
0x14004373d  call    SecFreePool
0x140043742  test    rdi, rdi
0x140043745  jz      short loc_140043754
0x140043747  mov     edx, 64446353h; Tag
0x14004374c  mov     rcx, rdi; P
0x14004374f  call    SecFreePool
0x140043754  mov     rcx, rbx; ListEntry
0x140043757  call    SecReleaseEtwDescriptorBuffer
0x14004375c  mov     eax, esi
0x14004375e  mov     rcx, [rbp+var_10]
0x140043762  xor     rcx, rsp; StackCookie
0x140043765  call    __security_check_cookie
0x14004376a  add     rsp, 60h
0x14004376e  pop     r15
0x140043770  pop     r14
0x140043772  pop     r13
0x140043774  pop     rdi
0x140043775  pop     rsi
0x140043776  pop     rbx
0x140043777  pop     rbp
0x140043778  retn
```
