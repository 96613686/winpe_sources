# PsmpGetNextApplication

- ea: `0x1800032a0`
- end: `0x1800034fd`
- name: `PsmpGetNextApplication`
- size: `605`
- prototype: `volatile signed __int32 *__fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001230`
- `0x180002410`
- `0x180002550`
- `0x1800037f4`
- `0x180016bcc`
- `0x18002a630`
- `0x18002a7d0`
- `0x18002b200`

## callees

- `0x1800032a0`
- `0x180009b40`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000335c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000335c`
- `ntdll!RtlAcquireSRWLockShared` at `0x180003306`
- `ntdll!RtlAcquireSRWLockShared` at `0x180003306`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034c5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034c5`

## pseudocode

```c
volatile signed __int32 *__fastcall PsmpGetNextApplication(__int64 a1, __int64 a2)
{
  signed __int32 v2; // edi
  __int64 v3; // r15
  char v4; // r13
  volatile signed __int32 *v5; // rbx
  __int64 v6; // r14
  _QWORD **v7; // rsi
  _QWORD **i; // rbp
  __int64 v9; // rdx
  __int64 v10; // r9
  _QWORD *v11; // r8
  signed __int32 v12; // eax
  char *v13; // rcx
  __int64 v14; // rax
  int v16; // eax
  _DWORD v18[2]; // [rsp+30h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-88h] BYREF
  char *v21; // [rsp+60h] [rbp-78h]
  int v22; // [rsp+68h] [rbp-70h]
  int v23; // [rsp+6Ch] [rbp-6Ch]
  _DWORD *v24; // [rsp+70h] [rbp-68h]
  __int64 v25; // [rsp+78h] [rbp-60h]
  char *v26; // [rsp+80h] [rbp-58h]
  int v27; // [rsp+88h] [rbp-50h]
  int v28; // [rsp+8Ch] [rbp-4Ch]

  v2 = 0;
  v3 = a2;
  if ( !a2 )
    v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( !v3 )
  {
    LODWORD(v6) = 0;
    i = (_QWORD **)(a1 + 72);
    goto LABEL_6;
  }
  v6 = *(unsigned int *)(v3 + 4);
  v7 = (_QWORD **)(v3 + 24);
  for ( i = (_QWORD **)(a1 + 24 * (v6 + 3)); ; v7 = i )
  {
    RtlAcquireSRWLockShared(i + 2);
    v11 = *v7;
    if ( *v7 != i )
    {
      while ( 1 )
      {
        v5 = (volatile signed __int32 *)(v11 - 3);
        _m_prefetchw(v11 - 3);
        v12 = *((_DWORD *)v11 - 6);
        if ( v12 > 0 )
          break;
LABEL_11:
        v11 = (_QWORD *)*v11;
        v2 = v12 + 1;
        if ( v11 == i )
          goto LABEL_14;
      }
      while ( 1 )
      {
        v10 = (unsigned int)v12;
        v9 = (unsigned int)v12;
        v12 = _InterlockedCompareExchange(v5, v12 + 1, v12);
        if ( v12 == (_DWORD)v9 )
          break;
        if ( v12 <= 0 )
          goto LABEL_11;
      }
      v4 = 1;
      v2 = v10 + 1;
    }
LABEL_14:
    RtlReleaseSRWLockShared(i + 2, v9, v11, v10);
    if ( v3 )
      PsmpDereferenceApplicationEx(v3, 0);
    if ( v4 )
      break;
    LODWORD(v6) = v6 + 1;
    if ( (_DWORD)v6 == 128 )
      return 0;
    v3 = 0;
    i += 3;
LABEL_6:
    ;
  }
  if ( !v5 )
    return 0;
  if ( (unsigned int)dword_18003F048 > 5 && (qword_18003F058 & 2) != 0 && (qword_18003F060 & 2) == qword_18003F060 )
  {
    v18[0] = v2;
    v13 = (char *)(v5 + 1760);
    v25 = 4;
    v24 = v18;
    if ( v5 == (volatile signed __int32 *)-7040LL )
    {
      v13 = byte_180034900;
      v16 = 2;
    }
    else
    {
      v14 = -1;
      while ( *(_WORD *)&v13[2 * v14++ + 2] != 0 )
        ;
      v16 = 2 * v14 + 2;
    }
    v27 = v16;
    *(_DWORD *)&EventDescriptor.Level = 5;
    v26 = v13;
    UserData.Ptr = (ULONGLONG)off_18003F050;
    v28 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_18003F050;
    v21 = byte_180038155;
    UserData.Reserved = 2;
    v22 = 41;
    v23 = 1;
    v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return v5;
}

```

## disassembly

```asm
0x1800032a0  mov     [rsp+arg_10], rbx
0x1800032a5  push    rbp
0x1800032a6  push    rsi
0x1800032a7  push    rdi
0x1800032a8  push    r12
0x1800032aa  push    r13
0x1800032ac  push    r14
0x1800032ae  push    r15
0x1800032b0  sub     rsp, 0A0h
0x1800032b7  mov     rax, cs:__security_cookie
0x1800032be  xor     rax, rsp
0x1800032c1  mov     [rsp+0D8h+var_48], rax
0x1800032c9  xor     eax, eax
0x1800032cb  xor     edi, edi
0x1800032cd  test    rdx, rdx
0x1800032d0  mov     r15, rdx
0x1800032d3  cmovz   r15, rax
0x1800032d7  xor     r13b, r13b
0x1800032da  xor     ebx, ebx
0x1800032dc  test    r15, r15
0x1800032df  jz      short loc_1800032F8
0x1800032e1  mov     r14d, [r15+4]
0x1800032e5  lea     rsi, [r15+18h]
0x1800032e9  lea     rbp, [r14+3]
0x1800032ed  lea     rbp, [rbp+rbp*2+0]
0x1800032f2  lea     rbp, [rcx+rbp*8]
0x1800032f6  jmp     short loc_180003302
0x1800032f8  xor     r14d, r14d
0x1800032fb  lea     rbp, [rcx+48h]
0x1800032ff  mov     rsi, rbp
0x180003302  lea     rcx, [rbp+10h]
0x180003306  call    cs:__imp_RtlAcquireSRWLockShared
0x18000330c  mov     r8, [rsi]
0x18000330f  cmp     r8, rbp
0x180003312  jz      short loc_180003358
0x180003314  nop     dword ptr [rax+00h]
0x180003318  nop     dword ptr [rax+rax+00000000h]
0x180003320  lea     rbx, [r8-18h]
0x180003324  prefetchw byte ptr [rbx]
0x180003327  mov     eax, [rbx]
0x180003329  test    eax, eax
0x18000332b  jle     short loc_180003344
0x18000332d  nop     dword ptr [rax]
0x180003330  mov     r9d, eax
0x180003333  lea     ecx, [rax+1]
0x180003336  mov     edx, eax
0x180003338  lock cmpxchg [rbx], ecx
0x18000333c  cmp     eax, edx
0x18000333e  jz      short loc_180003351
0x180003340  test    eax, eax
0x180003342  jg      short loc_180003330
0x180003344  mov     r8, [r8]
0x180003347  lea     edi, [rax+1]
0x18000334a  cmp     r8, rbp
0x18000334d  jnz     short loc_180003320
0x18000334f  jmp     short loc_180003358
0x180003351  mov     r13b, 1
0x180003354  lea     edi, [r9+1]
0x180003358  lea     rcx, [rbp+10h]
0x18000335c  call    cs:__imp_RtlReleaseSRWLockShared
0x180003362  test    r15, r15
0x180003365  jz      short loc_180003371
0x180003367  xor     edx, edx
0x180003369  mov     rcx, r15
0x18000336c  call    PsmpDereferenceApplicationEx
0x180003371  test    r13b, r13b
0x180003374  jnz     short loc_180003392
0x180003376  inc     r14d
0x180003379  cmp     r14d, 80h
0x180003380  jz      loc_1800034D0
0x180003386  xor     r15d, r15d
0x180003389  add     rbp, 18h
0x18000338d  jmp     loc_1800032FF
0x180003392  test    rbx, rbx
0x180003395  jz      loc_1800034D0
0x18000339b  mov     eax, cs:dword_18003F048
0x1800033a1  cmp     eax, 5
0x1800033a4  jbe     loc_1800034CB
0x1800033aa  mov     rcx, cs:qword_18003F060
0x1800033b1  mov     rax, cs:qword_18003F058
0x1800033b8  test    al, 2
0x1800033ba  jz      loc_1800034CB
0x1800033c0  mov     rax, rcx
0x1800033c3  and     eax, 2
0x1800033c6  cmp     rax, rcx
0x1800033c9  jnz     loc_1800034CB
0x1800033cf  xor     edx, edx
0x1800033d1  mov     [rsp+0D8h+var_A8], edi
0x1800033d5  lea     rcx, [rbx+1B80h]
0x1800033dc  mov     [rsp+0D8h+var_60], 4
0x1800033e5  lea     rax, [rsp+0D8h+var_A8]
0x1800033ea  mov     [rsp+0D8h+var_68], rax
0x1800033ef  test    rcx, rcx
0x1800033f2  jz      short loc_180003414
0x1800033f4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800033fb  nop     dword ptr [rax+rax+00h]
0x180003400  cmp     [rcx+rax*2+2], dx
0x180003405  lea     rax, [rax+1]
0x180003409  jnz     short loc_180003400
0x18000340b  lea     eax, ds:2[rax*2]
0x180003412  jmp     short loc_180003420
0x180003414  lea     rcx, byte_180034900
0x18000341b  mov     eax, 2
0x180003420  mov     [rsp+0D8h+var_50], eax
0x180003427  xor     r9d, r9d; RelatedActivityId
0x18000342a  movzx   eax, cs:word_18003814B
0x180003431  xor     r8d, r8d; ActivityId
0x180003434  mov     dword ptr [rsp+0D8h+EventDescriptor.Level], eax
0x180003438  mov     rax, cs:off_18003F050
0x18000343f  mov     [rsp+0D8h+var_58], rcx
0x180003447  lea     rcx, _TraceLoggingMetadataEnd
0x18000344e  mov     [rsp+0D8h+var_88.Ptr], rax
0x180003453  mov     [rsp+0D8h+var_4C], edx
0x18000345a  lea     rdx, [rsp+0D8h+EventDescriptor]; EventDescriptor
0x18000345f  mov     dword ptr [rsp+0D8h+EventDescriptor.Id], 0B000000h
0x180003467  mov     [rsp+0D8h+EventDescriptor.Keyword], 2
0x180003470  movzx   eax, word ptr [rax]
0x180003473  mov     [rsp+0D8h+var_88.Size], eax
0x180003477  lea     rax, byte_180038155
0x18000347e  mov     [rsp+0D8h+var_78], rax
0x180003483  lea     rax, _TraceLoggingMetadata
0x18000348a  sub     ecx, eax
0x18000348c  mov     dword ptr [rsp+0D8h+var_88.0Ch], 2
0x180003494  mov     [rsp+0D8h+var_70], 29h ; ')'
0x18000349c  lea     rax, [rsp+0D8h+var_88]
0x1800034a1  mov     [rsp+0D8h+var_6C], 1
0x1800034a9  mov     [rsp+0D8h+var_A4], ecx
0x1800034ad  mov     ecx, [rsp+0D8h+var_A4]
0x1800034b1  mov     rcx, cs:RegHandle; RegHandle
0x1800034b8  mov     [rsp+0D8h+UserData], rax; UserData
0x1800034bd  mov     [rsp+0D8h+UserDataCount], 4; UserDataCount
0x1800034c5  call    cs:__imp_EventWriteTransfer
0x1800034cb  mov     rax, rbx
0x1800034ce  jmp     short loc_1800034D2
0x1800034d0  xor     eax, eax
0x1800034d2  mov     rcx, [rsp+0D8h+var_48]
0x1800034da  xor     rcx, rsp; StackCookie
0x1800034dd  call    __security_check_cookie
0x1800034e2  mov     rbx, [rsp+0D8h+arg_10]
0x1800034ea  add     rsp, 0A0h
0x1800034f1  pop     r15
0x1800034f3  pop     r14
0x1800034f5  pop     r13
0x1800034f7  pop     r12
0x1800034f9  pop     rdi
0x1800034fa  pop     rsi
0x1800034fb  pop     rbp
0x1800034fc  retn
```
