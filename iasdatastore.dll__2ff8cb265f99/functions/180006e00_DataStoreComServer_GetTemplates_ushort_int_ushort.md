# DataStoreComServer::GetTemplates(ushort *,int *,ushort * *)

- ea: `0x180006e00`
- end: `0x180006ecc`
- name: `?GetTemplates@DataStoreComServer@@UEAAJPEAGPEAHPEAPEAG@Z`
- size: `204`
- prototype: `__int64 __fastcall(DataStoreServer **this, unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006e00`
- `0x180007150`
- `0x1800086c8`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006e8b`
- `KERNEL32!EnterCriticalSection` at `0x180006e8b`
- `KERNEL32!LeaveCriticalSection` at `0x180006ea9`
- `KERNEL32!LeaveCriticalSection` at `0x180006ea9`

## string_xrefs

- `0x180006e45`: `DataStoreComServer::GetTemplates(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::GetTemplates(
        DataStoreServer **this,
        unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  unsigned int Templates; // ebx
  const _com_error *v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+8h]

  if ( this[9] )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      Templates = ((int (__stdcall *)(DataStoreServer *, const unsigned __int16 *, int *, unsigned __int16 **))DataStoreServer::GetTemplates)(
                    this[9],
                    a2,
                    a3,
                    a4);
      LeaveCriticalSection(v9);
    }
    catch ( const _com_error *v11 )
    {
      v13 = *((_DWORD *)v11 + 2);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::GetTemplates() - Caught COM exception (%!hresult!)...");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
      }
      return v13;
    }
    return Templates;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::GetTemplates(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006e00  mov     [rsp+arg_8], rbx
0x180006e05  mov     [rsp+arg_10], rsi
0x180006e0a  push    rdi
0x180006e0b  push    r14
0x180006e0d  push    r15
0x180006e0f  sub     rsp, 40h
0x180006e13  mov     rsi, r9
0x180006e16  mov     r14, r8
0x180006e19  mov     r15, rdx
0x180006e1c  mov     rbx, rcx
0x180006e1f  cmp     qword ptr [rcx+48h], 0
0x180006e24  jnz     short loc_180006E7B
0x180006e26  lea     rcx, WPP_GLOBAL_Control
0x180006e2d  mov     rax, cs:WPP_GLOBAL_Control
0x180006e34  cmp     rax, rcx
0x180006e37  jz      short loc_180006E74
0x180006e39  cmp     byte ptr [rax+19h], 2
0x180006e3d  jb      short loc_180006E74
0x180006e3f  test    byte ptr [rax+1Ch], 10h
0x180006e43  jz      short loc_180006E74
0x180006e45  lea     rcx, aDatastorecomse_6; "DataStoreComServer::GetTemplates(), dat"...
0x180006e4c  call    WppDbgPrint
0x180006e51  mov     edx, 12h
0x180006e56  lea     r9, aNpsds; "NPSDS"
0x180006e5d  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e6b  mov     rcx, [rcx+10h]
0x180006e6f  call    WPP_SF_s
0x180006e74  mov     eax, 80004005h
0x180006e79  jmp     short loc_180006EB8
0x180006e7b  lea     rax, [rcx+8]
0x180006e7f  mov     [rsp+58h+arg_0], rax
0x180006e84  lea     rdi, [rcx+10h]
0x180006e88  mov     rcx, rdi; lpCriticalSection
0x180006e8b  call    cs:__imp_EnterCriticalSection
0x180006e91  nop
0x180006e92  mov     r9, rsi; unsigned __int16 **
0x180006e95  mov     r8, r14; int *
0x180006e98  mov     rdx, r15; unsigned __int16 *
0x180006e9b  mov     rcx, [rbx+48h]; this
0x180006e9f  call    ?GetTemplates@DataStoreServer@@QEAAJPEBGAEAHAEAPEAG@Z; DataStoreServer::GetTemplates(ushort const *,int &,ushort * &)
0x180006ea4  mov     ebx, eax
0x180006ea6  mov     rcx, rdi; lpCriticalSection
0x180006ea9  call    cs:__imp_LeaveCriticalSection
0x180006eaf  nop
0x180006eb0  jmp     short loc_180006EB6
0x180006eb2  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180006eb6  mov     eax, ebx
0x180006eb8  mov     rbx, [rsp+58h+arg_8]
0x180006ebd  mov     rsi, [rsp+58h+arg_10]
0x180006ec2  add     rsp, 40h
0x180006ec6  pop     r15
0x180006ec8  pop     r14
0x180006eca  pop     rdi
0x180006ecb  retn
```
