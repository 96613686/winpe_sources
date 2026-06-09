# DataStoreComServer::Reload(void)

- ea: `0x180006ee0`
- end: `0x180006f88`
- name: `?Reload@DataStoreComServer@@UEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(DataStoreServer **this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006ee0`
- `0x180007150`
- `0x18000a334`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006f59`
- `KERNEL32!EnterCriticalSection` at `0x180006f59`
- `KERNEL32!LeaveCriticalSection` at `0x180006f6e`
- `KERNEL32!LeaveCriticalSection` at `0x180006f6e`

## string_xrefs

- `0x180006f13`: `DataStoreComServer::Reload(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::Reload(DataStoreServer **this)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  unsigned int v4; // ebx
  const _com_error *v5; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+50h] [rbp+8h]

  if ( this[9] )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      v4 = DataStoreServer::Reload((const WCHAR *)this[9]);
      LeaveCriticalSection(v3);
    }
    catch ( const _com_error *v5 )
    {
      v7 = *((_DWORD *)v5 + 2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::Reload() - Caught COM exception (%!hresult!)...");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
      }
      return v7;
    }
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::Reload(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006ee0  mov     [rsp+arg_8], rbx
0x180006ee5  push    rdi
0x180006ee6  sub     rsp, 40h
0x180006eea  mov     rbx, rcx
0x180006eed  cmp     qword ptr [rcx+48h], 0
0x180006ef2  jnz     short loc_180006F49
0x180006ef4  lea     rcx, WPP_GLOBAL_Control
0x180006efb  mov     rax, cs:WPP_GLOBAL_Control
0x180006f02  cmp     rax, rcx
0x180006f05  jz      short loc_180006F42
0x180006f07  cmp     byte ptr [rax+19h], 2
0x180006f0b  jb      short loc_180006F42
0x180006f0d  test    byte ptr [rax+1Ch], 10h
0x180006f11  jz      short loc_180006F42
0x180006f13  lea     rcx, aDatastorecomse_4; "DataStoreComServer::Reload(), data not "...
0x180006f1a  call    WppDbgPrint
0x180006f1f  mov     edx, 16h
0x180006f24  lea     r9, aNpsds; "NPSDS"
0x180006f2b  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f39  mov     rcx, [rcx+10h]
0x180006f3d  call    WPP_SF_s
0x180006f42  mov     eax, 80004005h
0x180006f47  jmp     short loc_180006F7D
0x180006f49  lea     rax, [rcx+8]
0x180006f4d  mov     [rsp+48h+arg_0], rax
0x180006f52  lea     rdi, [rcx+10h]
0x180006f56  mov     rcx, rdi; lpCriticalSection
0x180006f59  call    cs:__imp_EnterCriticalSection
0x180006f5f  nop
0x180006f60  mov     rcx, [rbx+48h]; this
0x180006f64  call    ?Reload@DataStoreServer@@QEAAJXZ; DataStoreServer::Reload(void)
0x180006f69  mov     ebx, eax
0x180006f6b  mov     rcx, rdi; lpCriticalSection
0x180006f6e  call    cs:__imp_LeaveCriticalSection
0x180006f74  nop
0x180006f75  jmp     short loc_180006F7B
0x180006f77  mov     ebx, dword ptr [rsp+48h+arg_0]
0x180006f7b  mov     eax, ebx
0x180006f7d  mov     rbx, [rsp+48h+arg_8]
0x180006f82  add     rsp, 40h
0x180006f86  pop     rdi
0x180006f87  retn
```
