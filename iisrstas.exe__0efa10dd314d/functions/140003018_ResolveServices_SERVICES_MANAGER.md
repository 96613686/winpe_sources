# ResolveServices(SERVICES_MANAGER *)

- ea: `0x140003018`
- end: `0x140003101`
- name: `?ResolveServices@@YAJPEAVSERVICES_MANAGER@@@Z`
- size: `233`
- prototype: `signed int __fastcall(struct SERVICES_MANAGER *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140002ec0`
- `0x140003110`
- `0x1400031d0`
- `0x1400032a0`

## callees

- `0x140003018`
- `0x1400035a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003043`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000308b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400030bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400030c4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000308b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400030bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1400030c4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140003035`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140003035`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003073`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400030a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140003073`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400030a4`

## pseudocode

```c
signed int __fastcall ResolveServices(struct SERVICES_MANAGER *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  signed int result; // eax
  unsigned int v5; // edi
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rax
  __int64 v8; // rcx
  __int64 i; // rbx
  unsigned __int16 *v10[2]; // [rsp+20h] [rbp-38h]

  *(_OWORD *)v10 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = 0;
    v6 = OpenServiceW(v2, L"IISADMIN", 0xF01FFu);
    if ( v6 )
    {
      v10[0] = L"IISADMIN";
      v5 = 1;
      CloseServiceHandle(v6);
    }
    v7 = OpenServiceW(v3, L"WAS", 0xF01FFu);
    if ( v7 )
    {
      v8 = v5++;
      v10[v8] = L"WAS";
      CloseServiceHandle(v7);
    }
    CloseServiceHandle(v3);
    if ( *(_DWORD *)this )
    {
      return -2147467259;
    }
    else
    {
      result = 0;
      for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
      {
        result = SERVICES_MANAGER::InsertServiceName(this, v10[i]);
        if ( result < 0 )
          break;
        ++*(_DWORD *)this;
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140003018  push    rbx
0x14000301a  push    rsi
0x14000301b  push    rdi
0x14000301c  push    r14
0x14000301e  sub     rsp, 38h
0x140003022  xor     edx, edx; lpDatabaseName
0x140003024  mov     rsi, rcx
0x140003027  xorps   xmm0, xmm0
0x14000302a  xor     ecx, ecx; lpMachineName
0x14000302c  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x140003031  lea     r8d, [rdx+1]; dwDesiredAccess
0x140003035  call    cs:__imp_OpenSCManagerW
0x14000303b  mov     rbx, rax
0x14000303e  test    rax, rax
0x140003041  jnz     short loc_14000305E
0x140003043  call    cs:__imp_GetLastError
0x140003049  test    eax, eax
0x14000304b  jle     loc_1400030F7
0x140003051  movzx   eax, ax
0x140003054  or      eax, 80070000h
0x140003059  jmp     loc_1400030F7
0x14000305e  lea     r14, ServiceName; "IISADMIN"
0x140003065  mov     r8d, 0F01FFh; dwDesiredAccess
0x14000306b  mov     rdx, r14; lpServiceName
0x14000306e  mov     rcx, rbx; hSCManager
0x140003071  xor     edi, edi
0x140003073  call    cs:__imp_OpenServiceW
0x140003079  test    rax, rax
0x14000307c  jz      short loc_140003091
0x14000307e  mov     rcx, rax; hSCObject
0x140003081  mov     [rsp+58h+var_38], r14
0x140003086  mov     edi, 1
0x14000308b  call    cs:__imp_CloseServiceHandle
0x140003091  lea     r14, aWas; "WAS"
0x140003098  mov     r8d, 0F01FFh; dwDesiredAccess
0x14000309e  mov     rdx, r14; lpServiceName
0x1400030a1  mov     rcx, rbx; hSCManager
0x1400030a4  call    cs:__imp_OpenServiceW
0x1400030aa  test    rax, rax
0x1400030ad  jz      short loc_1400030C1
0x1400030af  mov     ecx, edi
0x1400030b1  inc     edi
0x1400030b3  mov     [rsp+rcx*8+58h+var_38], r14
0x1400030b8  mov     rcx, rax; hSCObject
0x1400030bb  call    cs:__imp_CloseServiceHandle
0x1400030c1  mov     rcx, rbx; hSCObject
0x1400030c4  call    cs:__imp_CloseServiceHandle
0x1400030ca  cmp     dword ptr [rsi], 0
0x1400030cd  jz      short loc_1400030D6
0x1400030cf  mov     eax, 80004005h
0x1400030d4  jmp     short loc_1400030F7
0x1400030d6  xor     eax, eax
0x1400030d8  xor     ebx, ebx
0x1400030da  test    edi, edi
0x1400030dc  jz      short loc_1400030F7
0x1400030de  mov     rdx, [rsp+rbx*8+58h+var_38]; unsigned __int16 *
0x1400030e3  mov     rcx, rsi; this
0x1400030e6  call    ?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z; SERVICES_MANAGER::InsertServiceName(ushort *)
0x1400030eb  test    eax, eax
0x1400030ed  js      short loc_1400030F7
0x1400030ef  inc     dword ptr [rsi]
0x1400030f1  inc     ebx
0x1400030f3  cmp     ebx, edi
0x1400030f5  jb      short loc_1400030DE
0x1400030f7  add     rsp, 38h
0x1400030fb  pop     r14
0x1400030fd  pop     rdi
0x1400030fe  pop     rsi
0x1400030ff  pop     rbx
0x140003100  retn
```
