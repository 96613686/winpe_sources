# DataStoreComServer::SetConfiguration(ushort *,ushort *)

- ea: `0x180006f90`
- end: `0x180007053`
- name: `?SetConfiguration@DataStoreComServer@@UEAAJPEAG0@Z`
- size: `195`
- prototype: `__int64 __fastcall(DataStoreServer **this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006f90`
- `0x180007150`
- `0x18000a4a0`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007017`
- `KERNEL32!EnterCriticalSection` at `0x180007017`
- `KERNEL32!LeaveCriticalSection` at `0x18000703d`
- `KERNEL32!LeaveCriticalSection` at `0x18000703d`

## string_xrefs

- `0x180006fcc`: `DataStoreComServer::SetConfiguration(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::SetConfiguration(
        DataStoreServer **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  unsigned int v8; // edi
  const _com_error *v9; // [rsp+20h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+68h] [rbp+20h]

  if ( this[9] )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    v10 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      v8 = ((int (__stdcall *)(DataStoreServer *, const unsigned __int16 *, const unsigned __int16 *))DataStoreServer::SetConfiguration)(
             this[9],
             a2,
             a3);
    }
    catch ( const _com_error *v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::SetConfiguration() - Caught COM exception...");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
      }
      v8 = *((_DWORD *)v9 + 2);
      v7 = v10;
    }
    LeaveCriticalSection(v7);
    return v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::SetConfiguration(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006f90  mov     [rsp+arg_8], rbx
0x180006f95  push    rsi
0x180006f96  push    rdi
0x180006f97  push    r14
0x180006f99  sub     rsp, 30h
0x180006f9d  mov     rsi, r8
0x180006fa0  mov     r14, rdx
0x180006fa3  mov     rdi, rcx
0x180006fa6  cmp     qword ptr [rcx+48h], 0
0x180006fab  jnz     short loc_180007002
0x180006fad  lea     rcx, WPP_GLOBAL_Control
0x180006fb4  mov     rax, cs:WPP_GLOBAL_Control
0x180006fbb  cmp     rax, rcx
0x180006fbe  jz      short loc_180006FFB
0x180006fc0  cmp     byte ptr [rax+19h], 2
0x180006fc4  jb      short loc_180006FFB
0x180006fc6  test    byte ptr [rax+1Ch], 10h
0x180006fca  jz      short loc_180006FFB
0x180006fcc  lea     rcx, aDatastorecomse_3; "DataStoreComServer::SetConfiguration(),"...
0x180006fd3  call    WppDbgPrint
0x180006fd8  mov     edx, 10h
0x180006fdd  lea     r9, aNpsds; "NPSDS"
0x180006fe4  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ff2  mov     rcx, [rcx+10h]
0x180006ff6  call    WPP_SF_s
0x180006ffb  mov     eax, 80004005h
0x180007000  jmp     short loc_180007045
0x180007002  lea     rax, [rcx+8]
0x180007006  mov     [rsp+48h+arg_0], rax
0x18000700b  lea     rbx, [rcx+10h]
0x18000700f  mov     [rsp+48h+arg_18], rbx
0x180007014  mov     rcx, rbx; lpCriticalSection
0x180007017  call    cs:__imp_EnterCriticalSection
0x18000701d  nop
0x18000701e  mov     r8, rsi; unsigned __int16 *
0x180007021  mov     rdx, r14; unsigned __int16 *
0x180007024  mov     rcx, [rdi+48h]; this
0x180007028  call    ?SetConfiguration@DataStoreServer@@QEAAJPEBG0@Z; DataStoreServer::SetConfiguration(ushort const *,ushort const *)
0x18000702d  mov     edi, eax
0x18000702f  jmp     short loc_18000703A
0x180007031  mov     edi, dword ptr [rsp+48h+arg_0]
0x180007035  mov     rbx, [rsp+48h+arg_18]
0x18000703a  mov     rcx, rbx; lpCriticalSection
0x18000703d  call    cs:__imp_LeaveCriticalSection
0x180007043  mov     eax, edi
0x180007045  mov     rbx, [rsp+48h+arg_8]
0x18000704a  add     rsp, 30h
0x18000704e  pop     r14
0x180007050  pop     rdi
0x180007051  pop     rsi
0x180007052  retn
```
