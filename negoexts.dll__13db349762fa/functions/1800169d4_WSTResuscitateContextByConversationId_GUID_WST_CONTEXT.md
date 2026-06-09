# WSTResuscitateContextByConversationId(_GUID *,_WST_CONTEXT * *)

- ea: `0x1800169d4`
- end: `0x180016bb7`
- name: `?WSTResuscitateContextByConversationId@@YAJPEAU_GUID@@PEAPEAU_WST_CONTEXT@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _GUID *, struct _WST_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001414`

## callees

- `0x180006db0`
- `0x18000b7d0`
- `0x18000ca08`
- `0x18000ec28`
- `0x180015aa8`
- `0x1800169d4`
- `0x18001ecee`
- `0x18001ed20`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x180016a81`
- `ntdll!RtlLookupElementGenericTable` at `0x180016a81`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b8e`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b8e`
- `ntdll!RtlDeleteElementGenericTable` at `0x180016ac8`
- `ntdll!RtlDeleteElementGenericTable` at `0x180016ac8`
- `ntdll!RtlEnterCriticalSection` at `0x180016a5e`
- `ntdll!RtlEnterCriticalSection` at `0x180016a5e`

## pseudocode

```c
__int64 __fastcall WSTResuscitateContextByConversationId(struct _GUID *a1, struct _WST_CONTEXT **a2)
{
  __int64 v4; // rax
  struct _WST_CONTEXT **v5; // rax
  struct basessp::_WST_CREDENTIAL *v6; // r8
  struct _WST_CONTEXT **v7; // rbx
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v12; // [rsp+40h] [rbp-148h] BYREF
  _QWORD Buffer[2]; // [rsp+48h] [rbp-140h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp-130h] BYREF
  __int128 v15; // [rsp+78h] [rbp-110h]
  int v16; // [rsp+F4h] [rbp-94h]

  memset_0(v14, 0, 0x118u);
  v15 = (__int128)*a1;
  Buffer[1] = 0;
  Buffer[0] = v14;
  v4 = (__int64)*a2;
  v12 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  v16 = *(_DWORD *)(v4 + 156);
  RtlEnterCriticalSection(&WSTGlobalZombieContextTableLock);
  WSTAgeContextTableNoLock(&WSTGlobalZombieContextTable, &v12);
  v5 = (struct _WST_CONTEXT **)RtlLookupElementGenericTable(&WSTGlobalZombieContextTable, Buffer);
  v7 = v5;
  if ( !v5 )
    goto LABEL_15;
  if ( (unsigned int)basessp::WSTCompareCreds(
                       *((basessp **)*v5 + 3),
                       *((struct basessp::_WST_CREDENTIAL **)*a2 + 3),
                       v6) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v10 = 15;
    goto LABEL_14;
  }
  WSTDereferenceContext(*a2);
  *a2 = *v7;
  if ( !RtlDeleteElementGenericTable(&WSTGlobalZombieContextTable, Buffer) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v10 = 14;
LABEL_14:
    WPP_SF_(v9[2], v10, &WPP_50a36a53767033d7400ef6f5774d89ed_Traceguids);
LABEL_15:
    v8 = -1073741275;
    goto LABEL_16;
  }
  _InterlockedCompareExchange((volatile signed __int32 *)*a2 + 4, 0, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qDDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(*((_QWORD *)*a2 + 3) + 44LL),
      *(_DWORD *)(*((_QWORD *)*a2 + 3) + 40LL),
      (__int64)*a2 + 168);
  v8 = 0;
LABEL_16:
  RtlLeaveCriticalSection(&WSTGlobalZombieContextTableLock);
  return v8;
}

```

## disassembly

```asm
0x1800169d4  mov     [rsp+arg_10], rbx
0x1800169d9  push    rdi
0x1800169da  sub     rsp, 180h
0x1800169e1  mov     rax, cs:__security_cookie
0x1800169e8  xor     rax, rsp
0x1800169eb  mov     [rsp+188h+var_18], rax
0x1800169f3  mov     rdi, rdx
0x1800169f6  mov     rbx, rcx
0x1800169f9  xor     edx, edx; Val
0x1800169fb  lea     rcx, [rsp+188h+var_130]; void *
0x180016a00  mov     r8d, 118h; Size
0x180016a06  call    memset_0
0x180016a0b  mov     r8d, ds:7FFE0004h
0x180016a13  mov     eax, 7FFE0320h
0x180016a18  shl     r8, 20h
0x180016a1c  mov     rax, [rax]
0x180016a1f  movups  xmm0, xmmword ptr [rbx]
0x180016a22  shl     rax, 8
0x180016a26  mul     r8
0x180016a29  movdqu  [rsp+188h+var_110], xmm0
0x180016a2f  lea     rax, [rsp+188h+var_130]
0x180016a34  mov     [rsp+188h+var_138], 0
0x180016a3d  mov     [rsp+188h+Buffer], rax
0x180016a42  mov     rax, [rdi]
0x180016a45  mov     [rsp+188h+var_148], rdx
0x180016a4a  mov     ecx, [rax+9Ch]
0x180016a50  mov     [rsp+188h+var_94], ecx
0x180016a57  lea     rcx, ?WSTGlobalZombieContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180016a5e  call    cs:__imp_RtlEnterCriticalSection
0x180016a64  lea     rdx, [rsp+188h+var_148]; unsigned __int64 *
0x180016a69  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180016a70  call    ?WSTAgeContextTableNoLock@@YAKPEAU_RTL_GENERIC_TABLE@@PEA_K@Z; WSTAgeContextTableNoLock(_RTL_GENERIC_TABLE *,unsigned __int64 *)
0x180016a75  lea     rdx, [rsp+188h+Buffer]; Buffer
0x180016a7a  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180016a81  call    cs:__imp_RtlLookupElementGenericTable
0x180016a87  mov     rbx, rax
0x180016a8a  test    rax, rax
0x180016a8d  jz      loc_180016B82
0x180016a93  mov     rdx, [rdi]
0x180016a96  mov     rcx, [rax]
0x180016a99  mov     rdx, [rdx+18h]; struct basessp::_WST_CREDENTIAL *
0x180016a9d  mov     rcx, [rcx+18h]; this
0x180016aa1  call    ?WSTCompareCreds@basessp@@YAHPEAU_WST_CREDENTIAL@1@0@Z; basessp::WSTCompareCreds(basessp::_WST_CREDENTIAL *,basessp::_WST_CREDENTIAL *)
0x180016aa6  test    eax, eax
0x180016aa8  jnz     loc_180016B54
0x180016aae  mov     rcx, [rdi]; struct _WST_CONTEXT *
0x180016ab1  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x180016ab6  mov     rax, [rbx]
0x180016ab9  lea     rdx, [rsp+188h+Buffer]; Buffer
0x180016abe  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180016ac5  mov     [rdi], rax
0x180016ac8  call    cs:__imp_RtlDeleteElementGenericTable
0x180016ace  test    al, al
0x180016ad0  jz      short loc_180016B34
0x180016ad2  mov     rdx, [rdi]
0x180016ad5  xor     ecx, ecx
0x180016ad7  lea     eax, [rcx+1]
0x180016ada  lock cmpxchg [rdx+10h], ecx
0x180016adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ae6  lea     rax, WPP_GLOBAL_Control
0x180016aed  cmp     rcx, rax
0x180016af0  jz      short loc_180016B30
0x180016af2  test    byte ptr [rcx+1Ch], 2
0x180016af6  jz      short loc_180016B30
0x180016af8  mov     r9, [rdi]
0x180016afb  mov     edx, 0Dh
0x180016b00  mov     rcx, [rcx+10h]; LoggerHandle
0x180016b04  mov     r8, [r9+18h]
0x180016b08  lea     rax, [r9+0A8h]
0x180016b0f  mov     [rsp+188h+var_158], rax; __int64
0x180016b14  mov     eax, [r8+28h]
0x180016b18  mov     dword ptr [rsp+188h+var_160], eax; char
0x180016b1c  mov     eax, [r8+2Ch]
0x180016b20  lea     r8, WPP_50a36a53767033d7400ef6f5774d89ed_Traceguids
0x180016b27  mov     dword ptr [rsp+188h+var_168], eax; char
0x180016b2b  call    WPP_SF_qDDZ
0x180016b30  xor     ebx, ebx
0x180016b32  jmp     short loc_180016B87
0x180016b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b3b  lea     rax, WPP_GLOBAL_Control
0x180016b42  cmp     rcx, rax
0x180016b45  jz      short loc_180016B82
0x180016b47  test    byte ptr [rcx+1Ch], 1
0x180016b4b  jz      short loc_180016B82
0x180016b4d  mov     edx, 0Eh
0x180016b52  jmp     short loc_180016B72
0x180016b54  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b5b  lea     rax, WPP_GLOBAL_Control
0x180016b62  cmp     rcx, rax
0x180016b65  jz      short loc_180016B82
0x180016b67  test    byte ptr [rcx+1Ch], 1
0x180016b6b  jz      short loc_180016B82
0x180016b6d  mov     edx, 0Fh
0x180016b72  mov     rcx, [rcx+10h]
0x180016b76  lea     r8, WPP_50a36a53767033d7400ef6f5774d89ed_Traceguids
0x180016b7d  call    WPP_SF_
0x180016b82  mov     ebx, 0C0000225h
0x180016b87  lea     rcx, ?WSTGlobalZombieContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180016b8e  call    cs:__imp_RtlLeaveCriticalSection
0x180016b94  mov     eax, ebx
0x180016b96  mov     rcx, [rsp+188h+var_18]
0x180016b9e  xor     rcx, rsp; StackCookie
0x180016ba1  call    __security_check_cookie
0x180016ba6  mov     rbx, [rsp+188h+arg_10]
0x180016bae  add     rsp, 180h
0x180016bb5  pop     rdi
0x180016bb6  retn
```
