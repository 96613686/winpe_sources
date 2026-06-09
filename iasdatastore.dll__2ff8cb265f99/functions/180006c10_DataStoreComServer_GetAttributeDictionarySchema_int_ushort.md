# DataStoreComServer::GetAttributeDictionarySchema(int *,ushort * *)

- ea: `0x180006c10`
- end: `0x180006cc3`
- name: `?GetAttributeDictionarySchema@DataStoreComServer@@UEAAJPEAHPEAPEAG@Z`
- size: `179`
- prototype: `int(DataStoreComServer *__hidden this, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006c10`
- `0x180007150`
- `0x180007fb4`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006c8f`
- `KERNEL32!EnterCriticalSection` at `0x180006c8f`
- `KERNEL32!LeaveCriticalSection` at `0x180006caa`
- `KERNEL32!LeaveCriticalSection` at `0x180006caa`

## string_xrefs

- `0x180006c49`: `DataStoreComServer::GetAttributeDictionarySchema(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::GetAttributeDictionarySchema(
        DataStoreServer **this,
        UINT *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int AttributeDictionarySchema; // ebx
  const _com_error *v9; // [rsp+20h] [rbp-38h] BYREF

  if ( this[9] )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      AttributeDictionarySchema = DataStoreServer::GetAttributeDictionarySchema(this[9], a2, a3);
      LeaveCriticalSection(v7);
    }
    catch ( const _com_error *v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::GetAttributeDictionarySchema() - Caught COM exception...");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
      }
      return *((unsigned int *)v9 + 2);
    }
    return AttributeDictionarySchema;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::GetAttributeDictionarySchema(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006c10  push    rbx
0x180006c12  push    rsi
0x180006c13  push    rdi
0x180006c14  push    r14
0x180006c16  sub     rsp, 38h
0x180006c1a  mov     rsi, r8
0x180006c1d  mov     r14, rdx
0x180006c20  mov     rbx, rcx
0x180006c23  cmp     qword ptr [rcx+48h], 0
0x180006c28  jnz     short loc_180006C7F
0x180006c2a  lea     rcx, WPP_GLOBAL_Control
0x180006c31  mov     rax, cs:WPP_GLOBAL_Control
0x180006c38  cmp     rax, rcx
0x180006c3b  jz      short loc_180006C78
0x180006c3d  cmp     byte ptr [rax+19h], 2
0x180006c41  jb      short loc_180006C78
0x180006c43  test    byte ptr [rax+1Ch], 10h
0x180006c47  jz      short loc_180006C78
0x180006c49  lea     rcx, aDatastorecomse_2; "DataStoreComServer::GetAttributeDiction"...
0x180006c50  call    WppDbgPrint
0x180006c55  mov     edx, 0Ah
0x180006c5a  lea     r9, aNpsds; "NPSDS"
0x180006c61  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006c68  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c6f  mov     rcx, [rcx+10h]
0x180006c73  call    WPP_SF_s
0x180006c78  mov     eax, 80004005h
0x180006c7d  jmp     short loc_180006CB9
0x180006c7f  lea     rax, [rcx+8]
0x180006c83  mov     [rsp+58h+arg_0], rax
0x180006c88  lea     rdi, [rcx+10h]
0x180006c8c  mov     rcx, rdi; lpCriticalSection
0x180006c8f  call    cs:__imp_EnterCriticalSection
0x180006c95  nop
0x180006c96  mov     r8, rsi; unsigned __int16 **
0x180006c99  mov     rdx, r14; int *
0x180006c9c  mov     rcx, [rbx+48h]; this
0x180006ca0  call    ?GetAttributeDictionarySchema@DataStoreServer@@QEAAJAEAHAEAPEAG@Z; DataStoreServer::GetAttributeDictionarySchema(int &,ushort * &)
0x180006ca5  mov     ebx, eax
0x180006ca7  mov     rcx, rdi; lpCriticalSection
0x180006caa  call    cs:__imp_LeaveCriticalSection
0x180006cb0  nop
0x180006cb1  jmp     short loc_180006CB7
0x180006cb3  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180006cb7  mov     eax, ebx
0x180006cb9  add     rsp, 38h
0x180006cbd  pop     r14
0x180006cbf  pop     rdi
0x180006cc0  pop     rsi
0x180006cc1  pop     rbx
0x180006cc2  retn
```
