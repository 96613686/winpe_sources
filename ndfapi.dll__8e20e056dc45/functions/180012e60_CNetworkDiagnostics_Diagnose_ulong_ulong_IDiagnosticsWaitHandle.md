# CNetworkDiagnostics::Diagnose(ulong,ulong,IDiagnosticsWaitHandle * *)

- ea: `0x180012e60`
- end: `0x180012f42`
- name: `?Diagnose@CNetworkDiagnostics@@UEAAJKKPEAPEAUIDiagnosticsWaitHandle@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *this, int, int, struct IDiagnosticsWaitHandle **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012384`
- `0x180012e60`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012e87`
- `KERNEL32!EnterCriticalSection` at `0x180012e87`
- `KERNEL32!LeaveCriticalSection` at `0x180012f27`
- `KERNEL32!LeaveCriticalSection` at `0x180012f27`
- `KERNEL32!CreateThread` at `0x180012ee4`
- `KERNEL32!CreateThread` at `0x180012ee4`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::Diagnose(
        CNetworkDiagnostics *this,
        int a2,
        int a3,
        struct IDiagnosticsWaitHandle **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v9; // edi
  HANDLE Thread; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( *((_DWORD *)this + 30) == 1 )
  {
    *((_QWORD *)this + 8) = *((_QWORD *)this + 2);
    *((_DWORD *)this + 18) = a2;
    *((_QWORD *)this + 10) = (char *)this + 48;
    *((_QWORD *)this + 11) = (char *)this + 120;
    *((_QWORD *)this + 13) = (char *)this + 24;
    *((_QWORD *)this + 14) = (char *)this + 32;
    *((_DWORD *)this + 24) = a3;
    Thread = CreateThread(0, 0, DiagnoseThread, (char *)this + 64, 0, 0);
    *((_QWORD *)this + 5) = Thread;
    if ( Thread )
    {
      v14 = 0;
      v9 = ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(v12, v11, &v14);
      if ( v9 >= 0 )
      {
        *(_QWORD *)(v14 + 72) = *((_QWORD *)this + 5);
        *a4 = (struct IDiagnosticsWaitHandle *)v14;
      }
    }
    else
    {
      v9 = -2147023842;
    }
  }
  else
  {
    v9 = -2147024120;
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012e60  mov     [rsp+arg_8], rbx
0x180012e65  mov     [rsp+arg_10], rbp
0x180012e6a  push    rsi
0x180012e6b  push    rdi
0x180012e6c  push    r14
0x180012e6e  sub     rsp, 30h
0x180012e72  lea     rsi, [rcx+80h]
0x180012e79  mov     rbx, rcx
0x180012e7c  mov     rcx, rsi; lpCriticalSection
0x180012e7f  mov     r14, r9
0x180012e82  mov     edi, r8d
0x180012e85  mov     ebp, edx
0x180012e87  call    cs:__imp_EnterCriticalSection
0x180012e8d  lea     rcx, [rbx+78h]
0x180012e91  cmp     dword ptr [rcx], 1
0x180012e94  jz      short loc_180012EA0
0x180012e96  mov     edi, 80070308h
0x180012e9b  jmp     loc_180012F24
0x180012ea0  mov     rax, [rbx+10h]
0x180012ea4  lea     r9, [rbx+40h]; lpParameter
0x180012ea8  mov     [r9], rax
0x180012eab  lea     r8, ?DiagnoseThread@@YAKPEAX@Z; lpStartAddress
0x180012eb2  lea     rax, [rbx+30h]
0x180012eb6  mov     [r9+8], ebp
0x180012eba  mov     [rbx+50h], rax
0x180012ebe  xor     ebp, ebp
0x180012ec0  lea     rax, [rbx+18h]
0x180012ec4  mov     [rbx+58h], rcx
0x180012ec8  mov     [rbx+68h], rax
0x180012ecc  xor     edx, edx; dwStackSize
0x180012ece  lea     rax, [rbx+20h]
0x180012ed2  mov     [rsp+48h+lpThreadId], rbp; lpThreadId
0x180012ed7  xor     ecx, ecx; lpThreadAttributes
0x180012ed9  mov     [rbx+70h], rax
0x180012edd  mov     [rbx+60h], edi
0x180012ee0  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x180012ee4  call    cs:__imp_CreateThread
0x180012eea  mov     [rbx+28h], rax
0x180012eee  test    rax, rax
0x180012ef1  jnz     short loc_180012EFA
0x180012ef3  mov     edi, 8007041Eh
0x180012ef8  jmp     short loc_180012F24
0x180012efa  lea     r8, [rsp+48h+arg_0]
0x180012eff  mov     [rsp+48h+arg_0], rbp
0x180012f04  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIDiagnosticsWaitHandle@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIDiagnosticsWaitHandle>>::CreateInstance(void *,_GUID const &,void * *)
0x180012f09  mov     edi, eax
0x180012f0b  test    eax, eax
0x180012f0d  js      short loc_180012F24
0x180012f0f  mov     rdx, [rsp+48h+arg_0]
0x180012f14  mov     r8, [rbx+28h]
0x180012f18  mov     [rdx+48h], r8
0x180012f1c  mov     rdx, [rsp+48h+arg_0]
0x180012f21  mov     [r14], rdx
0x180012f24  mov     rcx, rsi; lpCriticalSection
0x180012f27  call    cs:__imp_LeaveCriticalSection
0x180012f2d  mov     rbx, [rsp+48h+arg_8]
0x180012f32  mov     eax, edi
0x180012f34  mov     rbp, [rsp+48h+arg_10]
0x180012f39  add     rsp, 30h
0x180012f3d  pop     r14
0x180012f3f  pop     rdi
0x180012f40  pop     rsi
0x180012f41  retn
```
