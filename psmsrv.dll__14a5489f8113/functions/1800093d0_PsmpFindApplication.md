# PsmpFindApplication

- ea: `0x1800093d0`
- end: `0x180009628`
- name: `PsmpFindApplication`
- size: `600`
- prototype: `_QWORD *__fastcall(_QWORD **, __int64, WCHAR *, unsigned __int64)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000191c`
- `0x180007fd0`
- `0x180008360`
- `0x180008840`
- `0x180008cc0`
- `0x180008f10`
- `0x180009630`
- `0x18000b4d8`
- `0x18001a190`
- `0x18001aba0`
- `0x18002abe0`
- `0x18002afc0`
- `0x18002b470`
- `0x18002b760`
- `0x18002bd00`
- `0x18002bf90`
- `0x18002c250`

## callees

- `0x1800093d0`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800094b2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800094e2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800094b2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800094e2`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000941a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000941a`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000947f`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000947f`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009447`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009447`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000961a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000961a`

## pseudocode

```c
_QWORD *__fastcall PsmpFindApplication(_QWORD **a1, __int64 a2, WCHAR *a3, unsigned __int64 a4)
{
  _QWORD **v7; // r14
  int v8; // esi
  WCHAR *v9; // rdi
  WCHAR v10; // bx
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rsi
  signed __int32 *v16; // rbx
  signed __int32 v17; // eax
  int v19; // edi
  char *v20; // rcx
  __int64 v21; // rax
  int v23; // eax
  ULONG UserDataCount; // [rsp+20h] [rbp-B8h]
  _DWORD v25[2]; // [rsp+30h] [rbp-A8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-88h] BYREF
  char *v28; // [rsp+60h] [rbp-78h]
  int v29; // [rsp+68h] [rbp-70h]
  int v30; // [rsp+6Ch] [rbp-6Ch]
  _DWORD *v31; // [rsp+70h] [rbp-68h]
  __int64 v32; // [rsp+78h] [rbp-60h]
  char *v33; // [rsp+80h] [rbp-58h]
  int v34; // [rsp+88h] [rbp-50h]
  int v35; // [rsp+8Ch] [rbp-4Ch]

  v7 = a1;
  if ( !a1 )
  {
    v8 = 0;
    v9 = a3;
    do
    {
      v10 = *v9++;
      v11 = 37 * v8 + RtlUpcaseUnicodeChar(v10);
      v8 = v11;
    }
    while ( v10 );
    a4 = (char *)v9 - (char *)a3;
    v7 = (_QWORD **)(a2 + 24 * ((v11 & 0x7F) + 3LL));
  }
  RtlAcquireSRWLockShared(v7 + 2);
  v15 = *v7;
  if ( *v7 == v7 )
  {
LABEL_12:
    RtlReleaseSRWLockShared(v7 + 2, v12, v13, v14);
    return 0;
  }
  while ( 1 )
  {
    v16 = (signed __int32 *)(v15 - 3);
    if ( a4 == *(v15 - 1) )
    {
      LOBYTE(UserDataCount) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v16 + 1), a4 >> 1, a3, a4 >> 1, UserDataCount) )
      {
        _m_prefetchw(v16);
        v17 = *v16;
        if ( *v16 > 0 )
          break;
      }
    }
LABEL_11:
    v15 = (_QWORD *)*v15;
    if ( v15 == v7 )
      goto LABEL_12;
  }
  while ( 1 )
  {
    v13 = (unsigned int)v17;
    v12 = (unsigned int)v17;
    v17 = _InterlockedCompareExchange(v16, v17 + 1, v17);
    if ( v17 == (_DWORD)v12 )
      break;
    if ( v17 <= 0 )
      goto LABEL_11;
  }
  v19 = v13 + 1;
  RtlReleaseSRWLockShared(v7 + 2, v12, v13, v14);
  if ( v15 == (_QWORD *)24 )
    return 0;
  if ( (unsigned int)dword_18003F048 > 5 && (qword_18003F058 & 2) != 0 && (qword_18003F060 & 2) == qword_18003F060 )
  {
    v20 = (char *)(v16 + 1760);
    v25[0] = v19;
    v32 = 4;
    v31 = v25;
    if ( v15 == (_QWORD *)-7016LL )
    {
      v20 = byte_180034900;
      v23 = 2;
    }
    else
    {
      v21 = -1;
      while ( *(_WORD *)&v20[2 * v21++ + 2] != 0 )
        ;
      v23 = 2 * v21 + 2;
    }
    v34 = v23;
    *(_DWORD *)&EventDescriptor.Level = 5;
    v33 = v20;
    UserData.Ptr = (ULONGLONG)off_18003F050;
    v35 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_18003F050;
    v28 = byte_1800385A1;
    UserData.Reserved = 2;
    v29 = 41;
    v30 = 1;
    v25[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return v15 - 3;
}

```

## disassembly

```asm
0x1800093d0  push    rbx
0x1800093d2  push    rbp
0x1800093d3  push    rsi
0x1800093d4  push    rdi
0x1800093d5  push    r12
0x1800093d7  push    r14
0x1800093d9  sub     rsp, 0A8h
0x1800093e0  mov     rax, cs:__security_cookie
0x1800093e7  xor     rax, rsp
0x1800093ea  mov     [rsp+0D8h+var_48], rax
0x1800093f2  mov     [rsp+0D8h+var_38], r15
0x1800093fa  mov     r15, rdx
0x1800093fd  mov     rdi, r9
0x180009400  mov     r12, r8
0x180009403  mov     r14, rcx
0x180009406  test    rcx, rcx
0x180009409  jnz     short loc_180009443
0x18000940b  xor     esi, esi
0x18000940d  mov     rdi, r8
0x180009410  movzx   ebx, word ptr [rdi]
0x180009413  add     rdi, 2
0x180009417  movzx   ecx, bx; Source
0x18000941a  call    cs:__imp_RtlUpcaseUnicodeChar
0x180009420  movzx   ecx, ax
0x180009423  imul    eax, esi, 25h ; '%'
0x180009426  add     ecx, eax
0x180009428  mov     esi, ecx
0x18000942a  test    bx, bx
0x18000942d  jnz     short loc_180009410
0x18000942f  mov     eax, ecx
0x180009431  sub     rdi, r12
0x180009434  and     eax, 7Fh
0x180009437  add     rax, 3
0x18000943b  lea     rax, [rax+rax*2]
0x18000943f  lea     r14, [r15+rax*8]
0x180009443  lea     rcx, [r14+10h]
0x180009447  call    cs:__imp_RtlAcquireSRWLockShared
0x18000944d  mov     rsi, [r14]
0x180009450  mov     r15, [rsp+0D8h+var_38]
0x180009458  cmp     rsi, r14
0x18000945b  jz      short loc_1800094AE
0x18000945d  nop     dword ptr [rax]
0x180009460  cmp     rdi, [rsi-8]
0x180009464  lea     rbx, [rsi-18h]
0x180009468  jnz     short loc_1800094A6
0x18000946a  mov     rcx, [rbx+8]
0x18000946e  mov     rdx, rdi
0x180009471  shr     rdx, 1
0x180009474  mov     r8, r12
0x180009477  mov     r9, rdx
0x18000947a  mov     byte ptr [rsp+0D8h+UserDataCount], 1
0x18000947f  call    cs:__imp_RtlCompareUnicodeStrings
0x180009485  test    eax, eax
0x180009487  jnz     short loc_1800094A6
0x180009489  prefetchw byte ptr [rbx]
0x18000948c  mov     eax, [rbx]
0x18000948e  test    eax, eax
0x180009490  jle     short loc_1800094A6
0x180009492  mov     r8d, eax
0x180009495  lea     ecx, [rax+1]
0x180009498  mov     edx, eax
0x18000949a  lock cmpxchg [rbx], ecx
0x18000949e  cmp     eax, edx
0x1800094a0  jz      short loc_1800094DA
0x1800094a2  test    eax, eax
0x1800094a4  jg      short loc_180009492
0x1800094a6  mov     rsi, [rsi]
0x1800094a9  cmp     rsi, r14
0x1800094ac  jnz     short loc_180009460
0x1800094ae  lea     rcx, [r14+10h]
0x1800094b2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800094b8  xor     eax, eax
0x1800094ba  mov     rcx, [rsp+0D8h+var_48]
0x1800094c2  xor     rcx, rsp; StackCookie
0x1800094c5  call    __security_check_cookie
0x1800094ca  add     rsp, 0A8h
0x1800094d1  pop     r14
0x1800094d3  pop     r12
0x1800094d5  pop     rdi
0x1800094d6  pop     rsi
0x1800094d7  pop     rbp
0x1800094d8  pop     rbx
0x1800094d9  retn
0x1800094da  lea     rcx, [r14+10h]
0x1800094de  lea     edi, [r8+1]
0x1800094e2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800094e8  test    rbx, rbx
0x1800094eb  jz      short loc_1800094B8
0x1800094ed  mov     eax, cs:dword_18003F048
0x1800094f3  cmp     eax, 5
0x1800094f6  jbe     loc_180009620
0x1800094fc  mov     rcx, cs:qword_18003F060
0x180009503  mov     rax, cs:qword_18003F058
0x18000950a  test    al, 2
0x18000950c  jz      loc_180009620
0x180009512  mov     rax, rcx
0x180009515  and     eax, 2
0x180009518  cmp     rax, rcx
0x18000951b  jnz     loc_180009620
0x180009521  lea     rcx, [rbx+1B80h]
0x180009528  mov     [rsp+0D8h+var_A8], edi
0x18000952c  mov     [rsp+0D8h+var_60], 4
0x180009535  lea     rax, [rsp+0D8h+var_A8]
0x18000953a  mov     [rsp+0D8h+var_68], rax
0x18000953f  test    rcx, rcx
0x180009542  jz      short loc_180009565
0x180009544  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000954b  nop     dword ptr [rax+rax+00h]
0x180009550  cmp     word ptr [rcx+rax*2+2], 0
0x180009556  lea     rax, [rax+1]
0x18000955a  jnz     short loc_180009550
0x18000955c  lea     eax, ds:2[rax*2]
0x180009563  jmp     short loc_180009571
0x180009565  lea     rcx, byte_180034900
0x18000956c  mov     eax, 2
0x180009571  mov     [rsp+0D8h+var_50], eax
0x180009578  lea     rdx, [rsp+0D8h+EventDescriptor]; EventDescriptor
0x18000957d  movzx   eax, cs:word_180038597
0x180009584  xor     r9d, r9d; RelatedActivityId
0x180009587  mov     dword ptr [rsp+0D8h+EventDescriptor.Level], eax
0x18000958b  xor     r8d, r8d; ActivityId
0x18000958e  mov     rax, cs:off_18003F050
0x180009595  mov     [rsp+0D8h+var_58], rcx
0x18000959d  lea     rcx, _TraceLoggingMetadataEnd
0x1800095a4  mov     [rsp+0D8h+var_88.Ptr], rax
0x1800095a9  mov     [rsp+0D8h+var_4C], 0
0x1800095b4  mov     dword ptr [rsp+0D8h+EventDescriptor.Id], 0B000000h
0x1800095bc  mov     [rsp+0D8h+EventDescriptor.Keyword], 2
0x1800095c5  movzx   eax, word ptr [rax]
0x1800095c8  mov     [rsp+0D8h+var_88.Size], eax
0x1800095cc  lea     rax, byte_1800385A1
0x1800095d3  mov     [rsp+0D8h+var_78], rax
0x1800095d8  lea     rax, _TraceLoggingMetadata
0x1800095df  sub     ecx, eax
0x1800095e1  mov     dword ptr [rsp+0D8h+var_88.0Ch], 2
0x1800095e9  mov     [rsp+0D8h+var_70], 29h ; ')'
0x1800095f1  lea     rax, [rsp+0D8h+var_88]
0x1800095f6  mov     [rsp+0D8h+var_6C], 1
0x1800095fe  mov     [rsp+0D8h+var_A4], ecx
0x180009602  mov     ecx, [rsp+0D8h+var_A4]
0x180009606  mov     rcx, cs:RegHandle; RegHandle
0x18000960d  mov     [rsp+0D8h+UserData], rax; UserData
0x180009612  mov     [rsp+0D8h+UserDataCount], 4; UserDataCount
0x18000961a  call    cs:__imp_EventWriteTransfer
0x180009620  mov     rax, rbx
0x180009623  jmp     loc_1800094BA
```
