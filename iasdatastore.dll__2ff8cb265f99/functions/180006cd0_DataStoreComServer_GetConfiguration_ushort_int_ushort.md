# DataStoreComServer::GetConfiguration(ushort *,int *,ushort * *)

- ea: `0x180006cd0`
- end: `0x180006d9c`
- name: `?GetConfiguration@DataStoreComServer@@UEAAJPEAGPEAHPEAPEAG@Z`
- size: `204`
- prototype: `__int64 __fastcall(DataStoreServer **this, unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006cd0`
- `0x180007150`
- `0x1800081b8`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006d5b`
- `KERNEL32!EnterCriticalSection` at `0x180006d5b`
- `KERNEL32!LeaveCriticalSection` at `0x180006d79`
- `KERNEL32!LeaveCriticalSection` at `0x180006d79`

## string_xrefs

- `0x180006d15`: `DataStoreComServer::GetConfiguration(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::GetConfiguration(
        DataStoreServer **this,
        unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  unsigned int Configuration; // ebx
  const _com_error *v11; // [rsp+20h] [rbp-28h] BYREF

  if ( this[9] )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      Configuration = ((int (__stdcall *)(DataStoreServer *, const unsigned __int16 *, int *, unsigned __int16 **))DataStoreServer::GetConfiguration)(
                        this[9],
                        a2,
                        a3,
                        a4);
      LeaveCriticalSection(v9);
    }
    catch ( const _com_error *v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::GetConfiguration() - Caught COM exception...");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
      }
      return *((unsigned int *)v11 + 2);
    }
    return Configuration;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::GetConfiguration(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006cd0  mov     [rsp+arg_8], rbx
0x180006cd5  mov     [rsp+arg_10], rsi
0x180006cda  push    rdi
0x180006cdb  push    r14
0x180006cdd  push    r15
0x180006cdf  sub     rsp, 30h
0x180006ce3  mov     rsi, r9
0x180006ce6  mov     r14, r8
0x180006ce9  mov     r15, rdx
0x180006cec  mov     rbx, rcx
0x180006cef  cmp     qword ptr [rcx+48h], 0
0x180006cf4  jnz     short loc_180006D4B
0x180006cf6  lea     rcx, WPP_GLOBAL_Control
0x180006cfd  mov     rax, cs:WPP_GLOBAL_Control
0x180006d04  cmp     rax, rcx
0x180006d07  jz      short loc_180006D44
0x180006d09  cmp     byte ptr [rax+19h], 2
0x180006d0d  jb      short loc_180006D44
0x180006d0f  test    byte ptr [rax+1Ch], 10h
0x180006d13  jz      short loc_180006D44
0x180006d15  lea     rcx, aDatastorecomse_1; "DataStoreComServer::GetConfiguration(),"...
0x180006d1c  call    WppDbgPrint
0x180006d21  mov     edx, 0Eh
0x180006d26  lea     r9, aNpsds; "NPSDS"
0x180006d2d  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d3b  mov     rcx, [rcx+10h]
0x180006d3f  call    WPP_SF_s
0x180006d44  mov     eax, 80004005h
0x180006d49  jmp     short loc_180006D88
0x180006d4b  lea     rax, [rcx+8]
0x180006d4f  mov     [rsp+48h+arg_0], rax
0x180006d54  lea     rdi, [rcx+10h]
0x180006d58  mov     rcx, rdi; lpCriticalSection
0x180006d5b  call    cs:__imp_EnterCriticalSection
0x180006d61  nop
0x180006d62  mov     r9, rsi; unsigned __int16 **
0x180006d65  mov     r8, r14; int *
0x180006d68  mov     rdx, r15; unsigned __int16 *
0x180006d6b  mov     rcx, [rbx+48h]; this
0x180006d6f  call    ?GetConfiguration@DataStoreServer@@QEAAJPEBGAEAHAEAPEAG@Z; DataStoreServer::GetConfiguration(ushort const *,int &,ushort * &)
0x180006d74  mov     ebx, eax
0x180006d76  mov     rcx, rdi; lpCriticalSection
0x180006d79  call    cs:__imp_LeaveCriticalSection
0x180006d7f  nop
0x180006d80  jmp     short loc_180006D86
0x180006d82  mov     ebx, dword ptr [rsp+48h+arg_0]
0x180006d86  mov     eax, ebx
0x180006d88  mov     rbx, [rsp+48h+arg_8]
0x180006d8d  mov     rsi, [rsp+48h+arg_10]
0x180006d92  add     rsp, 30h
0x180006d96  pop     r15
0x180006d98  pop     r14
0x180006d9a  pop     rdi
0x180006d9b  retn
```
