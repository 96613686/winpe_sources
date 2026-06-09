# utIsServiceInstalled(__MIDL___MIDL_itf_catsrv_0000_0004_0001,ulong *,ulong *)

- ea: `0x18001f0b4`
- end: `0x18001f17f`
- name: `?utIsServiceInstalled@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@PEAK1@Z`
- size: `203`
- prototype: `int __high(enum __MIDL___MIDL_itf_catsrv_0000_0004_0001, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18001dfc0`
- `0x18001e550`

## callees

- `0x18001e744`
- `0x18001f014`
- `0x18001f0b4`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f157`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f165`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f157`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001f165`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f110`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001f110`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f131`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001f131`

## pseudocode

```c
__int64 __fastcall utIsServiceInstalled(int a1, _DWORD *a2, unsigned int *a3)
{
  __int64 v3; // rdi
  int LoadBalancingIfNeeded; // ebx
  const WCHAR *v7; // rdi
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbp
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rdi

  v3 = a1;
  if ( a1 == 1 )
  {
    LoadBalancingIfNeeded = LoadLoadBalancingIfNeeded(1);
    if ( LoadBalancingIfNeeded < 0 )
      return (unsigned int)LoadBalancingIfNeeded;
    if ( a2 )
    {
      *a2 = 0;
      v7 = (&csServices)[10 * v3 - 5];
      v8 = OpenSCManagerW(0, 0, 0x80000001);
      v9 = v8;
      if ( v8 )
      {
        v10 = OpenServiceW(v8, v7, 1u);
        v11 = v10;
        if ( v10 && (unsigned int)utGetServiceStartType(v10, a3) )
          *a2 = 1;
        CloseServiceHandle(v9);
        if ( v11 )
          CloseServiceHandle(v11);
      }
      else
      {
        return (unsigned int)-2147418113;
      }
      return (unsigned int)LoadBalancingIfNeeded;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001f0b4  push    rbx
0x18001f0b6  push    rbp
0x18001f0b7  push    rsi
0x18001f0b8  push    rdi
0x18001f0b9  push    r14
0x18001f0bb  sub     rsp, 20h
0x18001f0bf  movsxd  rdi, ecx
0x18001f0c2  mov     r14, r8
0x18001f0c5  mov     rsi, rdx
0x18001f0c8  lea     eax, [rdi-1]
0x18001f0cb  test    eax, eax
0x18001f0cd  jnz     loc_18001F16F
0x18001f0d3  mov     ecx, edi
0x18001f0d5  call    ?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z; LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)
0x18001f0da  mov     ebx, eax
0x18001f0dc  test    eax, eax
0x18001f0de  js      loc_18001F16B
0x18001f0e4  test    rsi, rsi
0x18001f0e7  jz      loc_18001F16F
0x18001f0ed  lea     rdx, [rdi+rdi*4]
0x18001f0f1  mov     dword ptr [rsi], 0
0x18001f0f7  add     rdx, rdx
0x18001f0fa  lea     rdi, ?csServices@@3PAUcsServiceInfo@@A; csServiceInfo near * csServices
0x18001f101  xor     ecx, ecx; lpMachineName
0x18001f103  mov     r8d, 80000001h; dwDesiredAccess
0x18001f109  mov     rdi, [rdi+rdx*8-50h]
0x18001f10e  xor     edx, edx; lpDatabaseName
0x18001f110  call    cs:__imp_OpenSCManagerW
0x18001f116  mov     rbp, rax
0x18001f119  test    rax, rax
0x18001f11c  jnz     short loc_18001F125
0x18001f11e  mov     ebx, 8000FFFFh
0x18001f123  jmp     short loc_18001F16B
0x18001f125  mov     r8d, 1; dwDesiredAccess
0x18001f12b  mov     rdx, rdi; lpServiceName
0x18001f12e  mov     rcx, rbp; hSCManager
0x18001f131  call    cs:__imp_OpenServiceW
0x18001f137  mov     rdi, rax
0x18001f13a  test    rax, rax
0x18001f13d  jz      short loc_18001F154
0x18001f13f  mov     rdx, r14; unsigned int *
0x18001f142  mov     rcx, rax; hService
0x18001f145  call    ?utGetServiceStartType@@YAHPEAUSC_HANDLE__@@PEAK@Z; utGetServiceStartType(SC_HANDLE__ *,ulong *)
0x18001f14a  test    eax, eax
0x18001f14c  jz      short loc_18001F154
0x18001f14e  mov     dword ptr [rsi], 1
0x18001f154  mov     rcx, rbp; hSCObject
0x18001f157  call    cs:__imp_CloseServiceHandle
0x18001f15d  test    rdi, rdi
0x18001f160  jz      short loc_18001F16B
0x18001f162  mov     rcx, rdi; hSCObject
0x18001f165  call    cs:__imp_CloseServiceHandle
0x18001f16b  mov     eax, ebx
0x18001f16d  jmp     short loc_18001F174
0x18001f16f  mov     eax, 80070057h
0x18001f174  add     rsp, 20h
0x18001f178  pop     r14
0x18001f17a  pop     rdi
0x18001f17b  pop     rsi
0x18001f17c  pop     rbp
0x18001f17d  pop     rbx
0x18001f17e  retn
```
