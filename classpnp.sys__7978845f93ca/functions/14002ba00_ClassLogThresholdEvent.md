# ClassLogThresholdEvent

- ea: `0x14002ba00`
- end: `0x14002bdc8`
- name: `ClassLogThresholdEvent`
- size: `968`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x1400134a0`
- `0x140014110`
- `0x14001fc38`
- `0x14002b2d4`
- `0x14002ba00`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x14002bc74`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14002bc74`
- `ntoskrnl!ExAllocatePool2` at `0x14002ba6f`
- `ntoskrnl!ExAllocatePool2` at `0x14002ba6f`
- `ntoskrnl!IoFreeWorkItem` at `0x14002bd90`
- `ntoskrnl!IoFreeWorkItem` at `0x14002bd90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd7c`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14002baa8`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14002baa8`

## pseudocode

```c
void __fastcall ClassLogThresholdEvent(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  _QWORD *DeviceExtension; // rsi
  __int64 v4; // rax
  __int64 v6; // rdx
  __int64 Pool2; // rax
  void *v8; // r12
  _WORD *ErrorLogEntry; // rax
  _WORD *v10; // rbx
  char *v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rax
  char *v14; // r14
  __int64 v15; // rax
  int v16; // r15d
  __int64 v17; // rax
  wchar_t *v18; // rcx
  NTSTATUS v19; // eax
  char v20; // cl
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  _QWORD *v27; // [rsp+30h] [rbp-98h]
  __int128 v28; // [rsp+38h] [rbp-90h] BYREF
  __int128 v29; // [rsp+48h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+58h] [rbp-70h] BYREF
  __int64 v31; // [rsp+78h] [rbp-50h]
  __int64 v32; // [rsp+80h] [rbp-48h]

  DeviceExtension = DeviceObject->DeviceExtension;
  v28 = 0;
  v29 = 0;
  v4 = DeviceExtension[66];
  v27 = DeviceExtension;
  if ( !v4 || (v6 = 184, *(_BYTE *)(v4 + 30) != 1) )
    v6 = 88;
  Pool2 = ExAllocatePool2(64, v6, 1094935379);
  v8 = (void *)Pool2;
  if ( !Pool2 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v22 = 70;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  ClassGetLBProvisioningResources((__int64)DeviceObject, Pool2, 0x20u, (__int64)&v28);
  ErrorLogEntry = IoAllocateErrorLogEntry(DeviceObject, 0x9Au);
  v10 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    memset(ErrorLogEntry, 0, 0x9Au);
    v10[3] = 48;
    v11 = (char *)(v10 + 24);
    if ( RtlStringCbPrintfW(v10 + 24, 0x6Au, (NTSTRSAFE_PCWSTR)"%\x00d", *((unsigned int *)DeviceExtension + 147)) >= 0 )
    {
      ++v10[2];
      if ( (BYTE8(v28) & 2) != 0 && (BYTE8(v28) & 1) != 0 )
      {
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v11[2 * v13] );
        v14 = &v11[2 * v13];
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v14[2 * v15 + 2] );
        v16 = 2 * (52 - v15);
        if ( RtlStringCbPrintfW((NTSTRSAFE_PWSTR)v14 + 1, v16, L"%I64u", *((_QWORD *)&v29 + 1)) < 0 )
        {
          DeviceExtension = v27;
        }
        else
        {
          ++v10[2];
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)&v14[2 * v17 + 2] );
          v18 = (wchar_t *)&v14[2 * v17 + 4];
          do
            ++v12;
          while ( v18[v12] );
          v19 = RtlStringCbPrintfW(v18, v16 - (2 * (int)v12 + 2), L"%I64u", (_QWORD)v29);
          DeviceExtension = v27;
          if ( v19 >= 0 )
            ++v10[2];
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
      }
    }
    if ( v10[2] != 3 )
    {
      *((_DWORD *)v10 + 3) = -2147221360;
      goto LABEL_38;
    }
    v20 = (BYTE12(v28) >> 2) & 3;
    if ( v20 == 1 )
    {
      if ( (BYTE12(v28) & 3) == 1 )
      {
        *((_DWORD *)v10 + 3) = -2147221358;
LABEL_38:
        IoWriteErrorLogEntry(v10);
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v22 = 68;
LABEL_50:
          WPP_SF_q(v21->AttachedDevice, v22, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, DeviceObject);
          goto LABEL_51;
        }
        goto LABEL_51;
      }
      if ( (BYTE12(v28) & 3) == 2 )
      {
        *((_DWORD *)v10 + 3) = -2147221357;
        goto LABEL_38;
      }
    }
    else if ( v20 == 2 )
    {
      if ( (BYTE12(v28) & 3) == 1 )
      {
        *((_DWORD *)v10 + 3) = -2147221356;
        goto LABEL_38;
      }
      if ( (BYTE12(v28) & 3) == 2 )
      {
        *((_DWORD *)v10 + 3) = -2147221355;
        goto LABEL_38;
      }
    }
    *((_DWORD *)v10 + 3) = -2147221359;
    goto LABEL_38;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v22 = 69;
    goto LABEL_50;
  }
LABEL_51:
  if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v21, 0x200000000000LL, 3) )
  {
    v26 = DeviceExtension[146];
    v32 = 16;
    v31 = v26 + 4;
    tlgWriteTransfer_EtwWriteTransfer(v23, (unsigned __int8 *)&word_140048E2E, v24, v25, v24, &v30);
  }
  _InterlockedExchange((volatile __int32 *)(DeviceExtension[144] + 96LL), 0);
  ClassReleaseRemoveLock(DeviceObject, Context);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  if ( Context )
    IoFreeWorkItem((PIO_WORKITEM)Context);
}

```

## disassembly

```asm
0x14002ba00  mov     [rsp+arg_10], rbx
0x14002ba05  push    rbp
0x14002ba06  push    rsi
0x14002ba07  push    rdi
0x14002ba08  push    r12
0x14002ba0a  push    r13
0x14002ba0c  push    r14
0x14002ba0e  push    r15
0x14002ba10  sub     rsp, 90h
0x14002ba17  mov     rax, cs:__security_cookie
0x14002ba1e  xor     rax, rsp
0x14002ba21  mov     [rsp+0C8h+var_40], rax
0x14002ba29  mov     rsi, [rcx+40h]
0x14002ba2d  xorps   xmm0, xmm0
0x14002ba30  movups  [rsp+0C8h+var_90], xmm0
0x14002ba35  xor     r15d, r15d
0x14002ba38  mov     r13, rdx
0x14002ba3b  movups  [rsp+0C8h+var_80], xmm0
0x14002ba40  mov     rax, [rsi+210h]
0x14002ba47  mov     rdi, rcx
0x14002ba4a  mov     [rsp+0C8h+var_98], rsi
0x14002ba4f  test    rax, rax
0x14002ba52  jz      short loc_14002BA5F
0x14002ba54  cmp     byte ptr [rax+1Eh], 1
0x14002ba58  mov     edx, 0B8h
0x14002ba5d  jz      short loc_14002BA64
0x14002ba5f  mov     edx, 58h ; 'X'
0x14002ba64  mov     ecx, 40h ; '@'
0x14002ba69  mov     r8d, 41436353h
0x14002ba6f  call    cs:__imp_ExAllocatePool2
0x14002ba76  nop     dword ptr [rax+rax+00h]
0x14002ba7b  mov     r12, rax
0x14002ba7e  mov     r8d, 3
0x14002ba84  test    rax, rax
0x14002ba87  jz      loc_14002BCC7
0x14002ba8d  lea     r9, [rsp+0C8h+var_90]
0x14002ba92  mov     r8d, 20h ; ' '
0x14002ba98  mov     rdx, rax
0x14002ba9b  mov     rcx, rdi
0x14002ba9e  call    ClassGetLBProvisioningResources
0x14002baa3  mov     dl, 9Ah; EntrySize
0x14002baa5  mov     rcx, rdi; IoObject
0x14002baa8  call    cs:__imp_IoAllocateErrorLogEntry
0x14002baaf  nop     dword ptr [rax+rax+00h]
0x14002bab4  mov     rbx, rax
0x14002bab7  test    rax, rax
0x14002baba  jz      loc_14002BCA0
0x14002bac0  xor     edx, edx; Val
0x14002bac2  mov     r8d, 9Ah; Size
0x14002bac8  mov     rcx, rax; void *
0x14002bacb  call    memset
0x14002bad0  mov     word ptr [rbx+6], 30h ; '0'
0x14002bad6  lea     r14, [rbx+30h]
0x14002bada  mov     r9d, [rsi+24Ch]
0x14002bae1  lea     r8, a0123456789abcd+10h; pszFormat
0x14002bae8  mov     rcx, r14; pszDest
0x14002baeb  mov     edx, 6Ah ; 'j'; cbDest
0x14002baf0  call    RtlStringCbPrintfW
0x14002baf5  lea     rbp, WPP_GLOBAL_Control
0x14002bafc  test    eax, eax
0x14002bafe  js      loc_14002BC04
0x14002bb04  inc     word ptr [rbx+4]
0x14002bb08  mov     al, byte ptr [rsp+0C8h+var_90+8]
0x14002bb0c  test    al, 2
0x14002bb0e  jz      loc_14002BBC4
0x14002bb14  test    al, 1
0x14002bb16  jz      loc_14002BBC4
0x14002bb1c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002bb20  mov     rax, rsi
0x14002bb23  inc     rax
0x14002bb26  cmp     [r14+rax*2], r15w
0x14002bb2b  jnz     short loc_14002BB23
0x14002bb2d  lea     r14, [r14+rax*2]
0x14002bb31  mov     rax, rsi
0x14002bb34  inc     rax
0x14002bb37  cmp     [r14+rax*2+2], r15w
0x14002bb3d  jnz     short loc_14002BB34
0x14002bb3f  mov     r9, qword ptr [rsp+0C8h+var_80+8]
0x14002bb44  lea     r8, aI64u; "%I64u"
0x14002bb4b  mov     r15d, 34h ; '4'
0x14002bb51  lea     rcx, [r14+2]; pszDest
0x14002bb55  sub     r15d, eax
0x14002bb58  add     r15d, r15d
0x14002bb5b  movsxd  rdx, r15d; cbDest
0x14002bb5e  call    RtlStringCbPrintfW
0x14002bb63  xor     edx, edx
0x14002bb65  test    eax, eax
0x14002bb67  js      loc_14002BBFC
0x14002bb6d  inc     word ptr [rbx+4]
0x14002bb71  mov     rax, rsi
0x14002bb74  inc     rax
0x14002bb77  cmp     [r14+rax*2+2], dx
0x14002bb7d  jnz     short loc_14002BB74
0x14002bb7f  lea     rcx, [r14+4]
0x14002bb83  lea     rcx, [rcx+rax*2]; pszDest
0x14002bb87  inc     rsi
0x14002bb8a  cmp     [rcx+rsi*2], dx
0x14002bb8e  jnz     short loc_14002BB87
0x14002bb90  mov     r9, qword ptr [rsp+0C8h+var_80]
0x14002bb95  lea     eax, ds:2[rsi*2]
0x14002bb9c  sub     r15d, eax
0x14002bb9f  lea     r8, aI64u; "%I64u"
0x14002bba6  movsxd  rdx, r15d; cbDest
0x14002bba9  call    RtlStringCbPrintfW
0x14002bbae  mov     rsi, [rsp+0C8h+var_98]
0x14002bbb3  xor     r15d, r15d
0x14002bbb6  lea     r14d, [r15+3]
0x14002bbba  test    eax, eax
0x14002bbbc  js      short loc_14002BC0A
0x14002bbbe  inc     word ptr [rbx+4]
0x14002bbc2  jmp     short loc_14002BC0A
0x14002bbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bbcb  mov     r14d, 3
0x14002bbd1  cmp     rcx, rbp
0x14002bbd4  jz      short loc_14002BC0A
0x14002bbd6  mov     eax, [rcx+2Ch]
0x14002bbd9  test    al, 1
0x14002bbdb  jz      short loc_14002BC0A
0x14002bbdd  cmp     [rcx+29h], r14b
0x14002bbe1  jb      short loc_14002BC0A
0x14002bbe3  mov     rcx, [rcx+18h]
0x14002bbe7  lea     edx, [r14+40h]
0x14002bbeb  mov     r9, rdi
0x14002bbee  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14002bbf5  call    WPP_SF_q
0x14002bbfa  jmp     short loc_14002BC0A
0x14002bbfc  mov     rsi, [rsp+0C8h+var_98]
0x14002bc01  xor     r15d, r15d
0x14002bc04  mov     r14d, 3
0x14002bc0a  cmp     [rbx+4], r14w
0x14002bc0f  jnz     short loc_14002BC6A
0x14002bc11  mov     al, byte ptr [rsp+0C8h+var_90+0Ch]
0x14002bc15  mov     cl, al
0x14002bc17  shr     cl, 2
0x14002bc1a  and     cl, r14b
0x14002bc1d  cmp     cl, 1
0x14002bc20  jnz     short loc_14002BC3F
0x14002bc22  and     al, r14b
0x14002bc25  cmp     al, cl
0x14002bc27  jnz     short loc_14002BC32
0x14002bc29  mov     dword ptr [rbx+0Ch], 80040092h
0x14002bc30  jmp     short loc_14002BC71
0x14002bc32  cmp     al, 2
0x14002bc34  jnz     short loc_14002BC61
0x14002bc36  mov     dword ptr [rbx+0Ch], 80040093h
0x14002bc3d  jmp     short loc_14002BC71
0x14002bc3f  cmp     cl, 2
0x14002bc42  jnz     short loc_14002BC61
0x14002bc44  and     al, r14b
0x14002bc47  cmp     al, 1
0x14002bc49  jnz     short loc_14002BC54
0x14002bc4b  mov     dword ptr [rbx+0Ch], 80040094h
0x14002bc52  jmp     short loc_14002BC71
0x14002bc54  cmp     al, 2
0x14002bc56  jnz     short loc_14002BC61
0x14002bc58  mov     dword ptr [rbx+0Ch], 80040095h
0x14002bc5f  jmp     short loc_14002BC71
0x14002bc61  mov     dword ptr [rbx+0Ch], 80040091h
0x14002bc68  jmp     short loc_14002BC71
0x14002bc6a  mov     dword ptr [rbx+0Ch], 80040090h
0x14002bc71  mov     rcx, rbx; ElEntry
0x14002bc74  call    cs:__imp_IoWriteErrorLogEntry
0x14002bc7b  nop     dword ptr [rax+rax+00h]
0x14002bc80  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc87  cmp     rcx, rbp
0x14002bc8a  jz      short loc_14002BCFF
0x14002bc8c  mov     eax, [rcx+2Ch]
0x14002bc8f  test    al, 1
0x14002bc91  jz      short loc_14002BCFF
0x14002bc93  cmp     byte ptr [rcx+29h], 4
0x14002bc97  jb      short loc_14002BCFF
0x14002bc99  mov     edx, 44h ; 'D'
0x14002bc9e  jmp     short loc_14002BCEC
0x14002bca0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bca7  lea     rbp, WPP_GLOBAL_Control
0x14002bcae  cmp     rcx, rbp
0x14002bcb1  jz      short loc_14002BCFF
0x14002bcb3  mov     eax, [rcx+2Ch]
0x14002bcb6  test    al, 1
0x14002bcb8  jz      short loc_14002BCFF
0x14002bcba  cmp     byte ptr [rcx+29h], 2
0x14002bcbe  jb      short loc_14002BCFF
0x14002bcc0  mov     edx, 45h ; 'E'
0x14002bcc5  jmp     short loc_14002BCEC
0x14002bcc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bcce  lea     rbp, WPP_GLOBAL_Control
0x14002bcd5  cmp     rcx, rbp
0x14002bcd8  jz      short loc_14002BD05
0x14002bcda  mov     eax, [rcx+2Ch]
0x14002bcdd  test    al, 1
0x14002bcdf  jz      short loc_14002BD05
0x14002bce1  cmp     byte ptr [rcx+29h], 2
0x14002bce5  jb      short loc_14002BD05
0x14002bce7  mov     edx, 46h ; 'F'
0x14002bcec  mov     rcx, [rcx+18h]
0x14002bcf0  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14002bcf7  mov     r9, rdi
0x14002bcfa  call    WPP_SF_q
0x14002bcff  mov     r8d, 3
0x14002bd05  mov     eax, cs:dword_14004D060
0x14002bd0b  cmp     eax, 5
0x14002bd0e  jbe     short loc_14002BD5A
0x14002bd10  mov     rdx, 200000000000h
0x14002bd1a  call    _tlgKeywordOn
0x14002bd1f  test    al, al
0x14002bd21  jz      short loc_14002BD5A
0x14002bd23  mov     rax, [rsi+490h]
0x14002bd2a  lea     rdx, word_140048E2E; int
0x14002bd31  add     rax, 4
0x14002bd35  mov     [rsp+0C8h+var_48], 10h
0x14002bd41  mov     [rsp+0C8h+var_50], rax
0x14002bd46  lea     rax, [rsp+0C8h+var_70]
0x14002bd4b  mov     [rsp+0C8h+var_A0], rax; __int64
0x14002bd50  mov     [rsp+0C8h+var_A8], r8d; ULONG
0x14002bd55  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002bd5a  mov     rdx, [rsi+480h]
0x14002bd61  mov     eax, r15d
0x14002bd64  mov     rcx, rdi; DeviceObject
0x14002bd67  xchg    eax, [rdx+60h]
0x14002bd6a  mov     rdx, r13; Tag
0x14002bd6d  call    ClassReleaseRemoveLock
0x14002bd72  test    r12, r12
0x14002bd75  jz      short loc_14002BD88
0x14002bd77  xor     edx, edx; Tag
0x14002bd79  mov     rcx, r12; P
0x14002bd7c  call    cs:__imp_ExFreePoolWithTag
0x14002bd83  nop     dword ptr [rax+rax+00h]
0x14002bd88  test    r13, r13
0x14002bd8b  jz      short loc_14002BD9C
0x14002bd8d  mov     rcx, r13; IoWorkItem
0x14002bd90  call    cs:__imp_IoFreeWorkItem
0x14002bd97  nop     dword ptr [rax+rax+00h]
0x14002bd9c  mov     rcx, [rsp+0C8h+var_40]
0x14002bda4  xor     rcx, rsp; StackCookie
0x14002bda7  call    __security_check_cookie
0x14002bdac  mov     rbx, [rsp+0C8h+arg_10]
0x14002bdb4  add     rsp, 90h
0x14002bdbb  pop     r15
0x14002bdbd  pop     r14
0x14002bdbf  pop     r13
0x14002bdc1  pop     r12
0x14002bdc3  pop     rdi
0x14002bdc4  pop     rsi
0x14002bdc5  pop     rbp
0x14002bdc6  retn
```
