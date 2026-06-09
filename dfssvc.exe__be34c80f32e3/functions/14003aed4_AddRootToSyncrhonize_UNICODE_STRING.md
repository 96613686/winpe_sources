# AddRootToSyncrhonize(_UNICODE_STRING *)

- ea: `0x14003aed4`
- end: `0x14003afa2`
- name: `?AddRootToSyncrhonize@@YAKPEAU_UNICODE_STRING@@@Z`
- size: `206`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b1dc`
- `0x140044f8c`

## callees

- `0x14003aed4`
- `0x14003afa8`
- `0x14003b5f0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14003af18`
- `ntdll!RtlCompareUnicodeString` at `0x14003af18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003aeef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003aeef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003af47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003af47`

## pseudocode

```c
__int64 __fastcall AddRootToSyncrhonize(struct _UNICODE_STRING *a1)
{
  unsigned int v2; // edi
  __int64 *i; // rbx
  char v4; // bl
  int v5; // edx
  int v6; // r8d

  v2 = 0;
  EnterCriticalSection(&stru_1400713F8);
  for ( i = (__int64 *)qword_140071420; i != &qword_140071420; i = (__int64 *)*i )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)i - 1, a1, 1u) )
    {
      v4 = 1;
      goto LABEL_7;
    }
  }
  v2 = AddToSyncList(a1);
  v4 = 0;
LABEL_7:
  LeaveCriticalSection(&stru_1400713F8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_ZdD(*((_QWORD *)pWppControl + 2), v5, v6, (_DWORD)a1, v4, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x14003aed4  mov     [rsp+arg_0], rbx
0x14003aed9  mov     [rsp+arg_8], rsi
0x14003aede  push    rdi
0x14003aedf  sub     rsp, 30h
0x14003aee3  mov     rsi, rcx
0x14003aee6  xor     edi, edi
0x14003aee8  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003aeef  call    cs:__imp_EnterCriticalSection
0x14003aef6  nop     dword ptr [rax+rax+00h]
0x14003aefb  mov     rbx, cs:qword_140071420
0x14003af02  lea     rax, qword_140071420
0x14003af09  cmp     rbx, rax
0x14003af0c  jz      short loc_14003AF34
0x14003af0e  lea     rcx, [rbx-10h]; String1
0x14003af12  mov     r8b, 1; CaseInsensitive
0x14003af15  mov     rdx, rsi; String2
0x14003af18  call    cs:__imp_RtlCompareUnicodeString
0x14003af1f  nop     dword ptr [rax+rax+00h]
0x14003af24  test    eax, eax
0x14003af26  jz      short loc_14003AF2D
0x14003af28  mov     rbx, [rbx]
0x14003af2b  jmp     short loc_14003AF02
0x14003af2d  mov     ebx, 1
0x14003af32  jmp     short loc_14003AF40
0x14003af34  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003af37  call    ?AddToSyncList@@YAKPEAU_UNICODE_STRING@@@Z; AddToSyncList(_UNICODE_STRING *)
0x14003af3c  mov     edi, eax
0x14003af3e  xor     ebx, ebx
0x14003af40  lea     rcx, stru_1400713F8; lpCriticalSection
0x14003af47  call    cs:__imp_LeaveCriticalSection
0x14003af4e  nop     dword ptr [rax+rax+00h]
0x14003af53  lea     rax, WPP_GLOBAL_Control
0x14003af5a  cmp     cs:WPP_GLOBAL_Control, rax
0x14003af61  jz      short loc_14003AF8F
0x14003af63  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003af6a  test    rcx, rcx
0x14003af6d  jz      short loc_14003AF8F
0x14003af6f  test    byte ptr [rcx+1Ch], 20h
0x14003af73  jz      short loc_14003AF8F
0x14003af75  cmp     byte ptr [rcx+19h], 1
0x14003af79  jb      short loc_14003AF8F
0x14003af7b  mov     rcx, [rcx+10h]
0x14003af7f  mov     r9, rsi
0x14003af82  mov     [rsp+38h+var_10], edi
0x14003af86  mov     [rsp+38h+var_18], ebx
0x14003af8a  call    WPP_SF_ZdD
0x14003af8f  mov     rbx, [rsp+38h+arg_0]
0x14003af94  mov     eax, edi
0x14003af96  mov     rsi, [rsp+38h+arg_8]
0x14003af9b  add     rsp, 30h
0x14003af9f  pop     rdi
0x14003afa0  retn
```
