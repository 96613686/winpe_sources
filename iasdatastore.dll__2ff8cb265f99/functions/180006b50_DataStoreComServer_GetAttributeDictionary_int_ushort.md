# DataStoreComServer::GetAttributeDictionary(int *,ushort * *)

- ea: `0x180006b50`
- end: `0x180006c03`
- name: `?GetAttributeDictionary@DataStoreComServer@@UEAAJPEAHPEAPEAG@Z`
- size: `179`
- prototype: `int(DataStoreComServer *__hidden this, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006b50`
- `0x180007150`
- `0x1800079fc`
- `0x18000d990`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006bcf`
- `KERNEL32!EnterCriticalSection` at `0x180006bcf`
- `KERNEL32!LeaveCriticalSection` at `0x180006bea`
- `KERNEL32!LeaveCriticalSection` at `0x180006bea`

## string_xrefs

- `0x180006b89`: `DataStoreComServer::GetAttributeDictionary(), data not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreComServer::GetAttributeDictionary(DataStoreServer **this, int *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int AttributeDictionary; // ebx
  const _com_error *v9; // [rsp+20h] [rbp-38h] BYREF

  if ( this[9] )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    try
    {
      AttributeDictionary = DataStoreServer::GetAttributeDictionary(this[9], a2, a3);
      LeaveCriticalSection(v7);
    }
    catch ( const _com_error *v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Error in DataStoreComServer::GetAttributeDictionary() - Caught COM exception...");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
      }
      return *((unsigned int *)v9 + 2);
    }
    return AttributeDictionary;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreComServer::GetAttributeDictionary(), data not initialized");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006b50  push    rbx
0x180006b52  push    rsi
0x180006b53  push    rdi
0x180006b54  push    r14
0x180006b56  sub     rsp, 38h
0x180006b5a  mov     rsi, r8
0x180006b5d  mov     r14, rdx
0x180006b60  mov     rbx, rcx
0x180006b63  cmp     qword ptr [rcx+48h], 0
0x180006b68  jnz     short loc_180006BBF
0x180006b6a  lea     rcx, WPP_GLOBAL_Control
0x180006b71  mov     rax, cs:WPP_GLOBAL_Control
0x180006b78  cmp     rax, rcx
0x180006b7b  jz      short loc_180006BB8
0x180006b7d  cmp     byte ptr [rax+19h], 2
0x180006b81  jb      short loc_180006BB8
0x180006b83  test    byte ptr [rax+1Ch], 10h
0x180006b87  jz      short loc_180006BB8
0x180006b89  lea     rcx, String1; "DataStoreComServer::GetAttributeDiction"...
0x180006b90  call    WppDbgPrint
0x180006b95  mov     edx, 0Ch
0x180006b9a  lea     r9, aNpsds; "NPSDS"
0x180006ba1  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x180006ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006baf  mov     rcx, [rcx+10h]
0x180006bb3  call    WPP_SF_s
0x180006bb8  mov     eax, 80004005h
0x180006bbd  jmp     short loc_180006BF9
0x180006bbf  lea     rax, [rcx+8]
0x180006bc3  mov     [rsp+58h+arg_0], rax
0x180006bc8  lea     rdi, [rcx+10h]
0x180006bcc  mov     rcx, rdi; lpCriticalSection
0x180006bcf  call    cs:__imp_EnterCriticalSection
0x180006bd5  nop
0x180006bd6  mov     r8, rsi; unsigned __int16 **
0x180006bd9  mov     rdx, r14; int *
0x180006bdc  mov     rcx, [rbx+48h]; this
0x180006be0  call    ?GetAttributeDictionary@DataStoreServer@@QEAAJAEAHAEAPEAG@Z; DataStoreServer::GetAttributeDictionary(int &,ushort * &)
0x180006be5  mov     ebx, eax
0x180006be7  mov     rcx, rdi; lpCriticalSection
0x180006bea  call    cs:__imp_LeaveCriticalSection
0x180006bf0  nop
0x180006bf1  jmp     short loc_180006BF7
0x180006bf3  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180006bf7  mov     eax, ebx
0x180006bf9  add     rsp, 38h
0x180006bfd  pop     r14
0x180006bff  pop     rdi
0x180006c00  pop     rsi
0x180006c01  pop     rbx
0x180006c02  retn
```
