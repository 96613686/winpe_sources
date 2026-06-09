# DataStoreComServer::SetTemplates(ushort *,ushort *)

- ea: `0x180007060`
- end: `0x180007113`
- name: `?SetTemplates@DataStoreComServer@@UEAAJPEAG0@Z`
- size: `179`
- prototype: `__int64 __fastcall(DataStoreServer **this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007060`
- `0x180007150`
- `0x18000b210`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800070df`
- `KERNEL32!EnterCriticalSection` at `0x1800070df`
- `KERNEL32!LeaveCriticalSection` at `0x1800070fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800070fa`

## string_xrefs

- `0x180007099`: `DataStoreComServer::SetTemplates(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::SetTemplates(DataStoreServer **this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int v8; // ebx
  const _com_error *v9; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+70h] [rbp+8h]

  if ( this[9] )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      v8 = DataStoreServer::SetTemplates(this[9], a2, a3);
      LeaveCriticalSection(v7);
    }
    catch ( const _com_error *v9 )
    {
      v11 = *((_DWORD *)v9 + 2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::SetTemplates() - Caught COM exception (%!hresult!)...");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
      }
      return v11;
    }
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::SetTemplates(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180007060  push    rbx
0x180007062  push    rsi
0x180007063  push    rdi
0x180007064  push    r14
0x180007066  sub     rsp, 48h
0x18000706a  mov     rsi, r8
0x18000706d  mov     r14, rdx
0x180007070  mov     rbx, rcx
0x180007073  cmp     qword ptr [rcx+48h], 0
0x180007078  jnz     short loc_1800070CF
0x18000707a  lea     rcx, WPP_GLOBAL_Control
0x180007081  mov     rax, cs:WPP_GLOBAL_Control
0x180007088  cmp     rax, rcx
0x18000708b  jz      short loc_1800070C8
0x18000708d  cmp     byte ptr [rax+19h], 2
0x180007091  jb      short loc_1800070C8
0x180007093  test    byte ptr [rax+1Ch], 10h
0x180007097  jz      short loc_1800070C8
0x180007099  lea     rcx, aDatastorecomse_0; "DataStoreComServer::SetTemplates(), dat"...
0x1800070a0  call    WppDbgPrint
0x1800070a5  mov     edx, 14h
0x1800070aa  lea     r9, aNpsds; "NPSDS"
0x1800070b1  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x1800070b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070bf  mov     rcx, [rcx+10h]
0x1800070c3  call    WPP_SF_s
0x1800070c8  mov     eax, 80004005h
0x1800070cd  jmp     short loc_180007109
0x1800070cf  lea     rax, [rcx+8]
0x1800070d3  mov     [rsp+68h+arg_0], rax
0x1800070d8  lea     rdi, [rcx+10h]
0x1800070dc  mov     rcx, rdi; lpCriticalSection
0x1800070df  call    cs:__imp_EnterCriticalSection
0x1800070e5  nop
0x1800070e6  mov     r8, rsi; unsigned __int16 *
0x1800070e9  mov     rdx, r14; unsigned __int16 *
0x1800070ec  mov     rcx, [rbx+48h]; this
0x1800070f0  call    ?SetTemplates@DataStoreServer@@QEAAJPEBG0@Z; DataStoreServer::SetTemplates(ushort const *,ushort const *)
0x1800070f5  mov     ebx, eax
0x1800070f7  mov     rcx, rdi; lpCriticalSection
0x1800070fa  call    cs:__imp_LeaveCriticalSection
0x180007100  nop
0x180007101  jmp     short loc_180007107
0x180007103  mov     ebx, dword ptr [rsp+68h+arg_0]
0x180007107  mov     eax, ebx
0x180007109  add     rsp, 48h
0x18000710d  pop     r14
0x18000710f  pop     rdi
0x180007110  pop     rsi
0x180007111  pop     rbx
0x180007112  retn
```
