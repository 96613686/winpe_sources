# CFile::SetSecurity(void *)

- ea: `0x18003a124`
- end: `0x18003a1f6`
- name: `?SetSecurity@CFile@@QEAAXPEAX@Z`
- size: `210`
- prototype: `void(CFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180039290`

## callees

- `0x18002a660`
- `0x18003a124`
- `0x1800a7558`
- `0x1800f9954`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a190`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18003a151`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18003a15c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18003a151`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18003a15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a1b3`

## pseudocode

```c
void __fastcall CFile::SetSecurity(CFile *this, void *a2)
{
  const void *v2; // rsi
  ULONG v5; // ebp
  __int64 v6; // rsi
  DWORD LastError; // eax

  v2 = (const void *)*((_QWORD *)this + 38);
  if ( v2 )
  {
    if ( a2 )
    {
      v5 = RtlLengthSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)this + 38));
      if ( v5 == RtlLengthSecurityDescriptor(a2) && !memcmp_0(v2, a2, v5) )
        return;
    }
  }
  else if ( !a2 )
  {
    return;
  }
  v6 = *((_QWORD *)this + 38);
  if ( v6
    && !HeapFree(hBitsHeap, 0, *((LPVOID *)this + 38))
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v6, LastError);
  }
  *((_QWORD *)this + 38) = a2;
  CFile::TriggerSerialization((__int64)this, 0);
}

```

## disassembly

```asm
0x18003a124  push    rbx
0x18003a126  push    rbp
0x18003a127  push    rsi
0x18003a128  push    rdi
0x18003a129  sub     rsp, 38h
0x18003a12d  mov     rsi, [rcx+130h]
0x18003a134  mov     rbx, rdx
0x18003a137  mov     rdi, rcx
0x18003a13a  test    rsi, rsi
0x18003a13d  jnz     short loc_18003A149
0x18003a13f  test    rdx, rdx
0x18003a142  jnz     short loc_18003A178
0x18003a144  jmp     loc_18003A1ED
0x18003a149  test    rbx, rbx
0x18003a14c  jz      short loc_18003A178
0x18003a14e  mov     rcx, rsi; SecurityDescriptor
0x18003a151  call    cs:__imp_RtlLengthSecurityDescriptor
0x18003a157  mov     rcx, rbx; SecurityDescriptor
0x18003a15a  mov     ebp, eax
0x18003a15c  call    cs:__imp_RtlLengthSecurityDescriptor
0x18003a162  cmp     ebp, eax
0x18003a164  jnz     short loc_18003A178
0x18003a166  mov     r8d, ebp; Size
0x18003a169  mov     rdx, rbx; Buf2
0x18003a16c  mov     rcx, rsi; Buf1
0x18003a16f  call    memcmp_0
0x18003a174  test    eax, eax
0x18003a176  jz      short loc_18003A1ED
0x18003a178  mov     rsi, [rdi+130h]
0x18003a17f  test    rsi, rsi
0x18003a182  jz      short loc_18003A1DC
0x18003a184  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18003a18b  mov     r8, rsi; lpMem
0x18003a18e  xor     edx, edx; dwFlags
0x18003a190  call    cs:__imp_HeapFree
0x18003a196  test    eax, eax
0x18003a198  jnz     short loc_18003A1DC
0x18003a19a  mov     rax, cs:WPP_GLOBAL_Control
0x18003a1a1  lea     rcx, WPP_GLOBAL_Control
0x18003a1a8  cmp     rax, rcx
0x18003a1ab  jz      short loc_18003A1DC
0x18003a1ad  test    byte ptr [rax+1Ch], 4
0x18003a1b1  jz      short loc_18003A1DC
0x18003a1b3  call    cs:__imp_GetLastError
0x18003a1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1c0  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18003a1c7  mov     edx, 0Bh
0x18003a1cc  mov     [rsp+58h+var_38], eax
0x18003a1d0  mov     r9, rsi
0x18003a1d3  mov     rcx, [rcx+10h]
0x18003a1d7  call    WPP_SF_qD
0x18003a1dc  xor     edx, edx
0x18003a1de  mov     [rdi+130h], rbx
0x18003a1e5  mov     rcx, rdi
0x18003a1e8  call    ?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z; CFile::TriggerSerialization(CFile::SerializationBehavior)
0x18003a1ed  add     rsp, 38h
0x18003a1f1  pop     rdi
0x18003a1f2  pop     rsi
0x18003a1f3  pop     rbp
0x18003a1f4  pop     rbx
0x18003a1f5  retn
```
