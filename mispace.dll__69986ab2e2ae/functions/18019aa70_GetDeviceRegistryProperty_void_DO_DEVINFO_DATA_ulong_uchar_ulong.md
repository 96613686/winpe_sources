# GetDeviceRegistryProperty(void *,_DO_DEVINFO_DATA *,ulong,uchar * *,ulong)

- ea: `0x18019aa70`
- end: `0x18019ac5f`
- name: `?GetDeviceRegistryProperty@@YAKPEAXPEAU_DO_DEVINFO_DATA@@KPEAPEAEK@Z`
- size: `495`
- prototype: `unsigned int __fastcall(void *, struct _DO_DEVINFO_DATA *, unsigned int, unsigned __int8 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1801a1fac`

## callees

- `0x1800298d0`
- `0x18019aa70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aaf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019abb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019abfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aaf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019abb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019abfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ac19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ab3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019ac19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019ab5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18019ab5e`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019aaea`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019ab9d`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019abed`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019aaea`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019ab9d`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18019abed`

## pseudocode

```c
DWORD __fastcall GetDeviceRegistryProperty(void *a1, struct _DO_DEVINFO_DATA *a2, __int64 a3, unsigned __int8 **a4)
{
  DWORD result; // eax
  int DeviceRegistryProperty; // ebx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v11; // edx
  HANDLE v12; // rax
  unsigned __int8 *v13; // rax

  if ( !a4 )
    return 87;
  while ( 1 )
  {
    DeviceRegistryProperty = DevObjGetDeviceRegistryProperty(a1, a2, 12);
    result = GetLastError();
    if ( !DeviceRegistryProperty && result != 122 )
      break;
    v9 = *a4;
    if ( *a4 )
    {
      ProcessHeap = GetProcessHeap();
      PmHeapFree(ProcessHeap, v11, v9);
      *a4 = 0;
    }
    v12 = GetProcessHeap();
    if ( !v12 )
    {
      *a4 = 0;
      return 8;
    }
    v13 = (unsigned __int8 *)HeapAlloc(v12, 8u, 0);
    *a4 = v13;
    if ( !v13 )
      return 8;
    if ( !(unsigned int)DevObjGetDeviceRegistryProperty(a1, a2, 12) )
      GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x18019aa70  mov     rax, rsp
0x18019aa73  mov     [rax+8], rbx
0x18019aa77  mov     [rax+10h], rbp
0x18019aa7b  mov     [rax+18h], r8d
0x18019aa7f  push    rsi
0x18019aa80  push    rdi
0x18019aa81  push    r12
0x18019aa83  push    r14
0x18019aa85  push    r15
0x18019aa87  sub     rsp, 40h
0x18019aa8b  mov     dword ptr [rax+18h], 0
0x18019aa92  mov     rdi, r9
0x18019aa95  mov     r15, rdx
0x18019aa98  mov     r12, rcx
0x18019aa9b  test    r9, r9
0x18019aa9e  jnz     short loc_18019AAA9
0x18019aaa0  lea     eax, [r9+57h]
0x18019aaa4  jmp     loc_18019AC47
0x18019aaa9  xor     esi, esi
0x18019aaab  xor     ebx, ebx
0x18019aaad  xor     ebp, ebp
0x18019aaaf  xor     r14b, r14b
0x18019aab2  test    esi, esi
0x18019aab4  jz      short loc_18019AABF
0x18019aab6  cmp     ebx, 7Ah ; 'z'
0x18019aab9  jnz     loc_18019ABC6
0x18019aabf  xor     r9d, r9d
0x18019aac2  lea     rax, [rsp+68h+dwBytes]
0x18019aaca  mov     [rsp+68h+var_38], rax
0x18019aacf  mov     rdx, r15
0x18019aad2  mov     [rsp+68h+var_40], 0
0x18019aada  mov     rcx, r12
0x18019aadd  mov     [rsp+68h+var_48], 0
0x18019aae6  lea     r8d, [r9+0Ch]
0x18019aaea  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18019aaf1  nop     dword ptr [rax+rax+00h]
0x18019aaf6  mov     ebx, eax
0x18019aaf8  call    cs:__imp_GetLastError
0x18019aaff  nop     dword ptr [rax+rax+00h]
0x18019ab04  test    ebx, ebx
0x18019ab06  jnz     short loc_18019AB11
0x18019ab08  cmp     eax, 7Ah ; 'z'
0x18019ab0b  jnz     loc_18019AC47
0x18019ab11  mov     rbx, [rdi]
0x18019ab14  test    rbx, rbx
0x18019ab17  jz      short loc_18019AB37
0x18019ab19  call    cs:__imp_GetProcessHeap
0x18019ab20  nop     dword ptr [rax+rax+00h]
0x18019ab25  mov     rcx, rax; void *
0x18019ab28  mov     r8, rbx; void *
0x18019ab2b  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x18019ab30  mov     qword ptr [rdi], 0
0x18019ab37  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x18019ab3e  call    cs:__imp_GetProcessHeap
0x18019ab45  nop     dword ptr [rax+rax+00h]
0x18019ab4a  test    rax, rax
0x18019ab4d  jz      loc_18019AC3B
0x18019ab53  mov     r8d, ebx; dwBytes
0x18019ab56  mov     edx, 8; dwFlags
0x18019ab5b  mov     rcx, rax; hHeap
0x18019ab5e  call    cs:__imp_HeapAlloc
0x18019ab65  nop     dword ptr [rax+rax+00h]
0x18019ab6a  mov     [rdi], rax
0x18019ab6d  test    rax, rax
0x18019ab70  jz      loc_18019AC42
0x18019ab76  mov     esi, dword ptr [rsp+68h+dwBytes]
0x18019ab7d  xor     ebx, ebx
0x18019ab7f  mov     [rsp+68h+var_38], rbx
0x18019ab84  xor     r9d, r9d
0x18019ab87  mov     [rsp+68h+var_40], esi
0x18019ab8b  mov     rdx, r15
0x18019ab8e  mov     rcx, r12
0x18019ab91  mov     [rsp+68h+var_48], rax
0x18019ab96  lea     r8d, [rbx+0Ch]
0x18019ab9a  mov     r14b, 1
0x18019ab9d  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18019aba4  nop     dword ptr [rax+rax+00h]
0x18019aba9  mov     ebp, eax
0x18019abab  test    eax, eax
0x18019abad  jnz     loc_18019AAB2
0x18019abb3  call    cs:__imp_GetLastError
0x18019abba  nop     dword ptr [rax+rax+00h]
0x18019abbf  mov     ebx, eax
0x18019abc1  jmp     loc_18019AAB2
0x18019abc6  test    r14b, r14b
0x18019abc9  jnz     short loc_18019AC0D
0x18019abcb  mov     rax, [rdi]
0x18019abce  xor     r9d, r9d
0x18019abd1  mov     [rsp+68h+var_38], 0
0x18019abda  mov     rdx, r15
0x18019abdd  mov     [rsp+68h+var_40], esi
0x18019abe1  mov     rcx, r12
0x18019abe4  mov     [rsp+68h+var_48], rax
0x18019abe9  lea     r8d, [r9+0Ch]
0x18019abed  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18019abf4  nop     dword ptr [rax+rax+00h]
0x18019abf9  test    eax, eax
0x18019abfb  jnz     short loc_18019AC37
0x18019abfd  call    cs:__imp_GetLastError
0x18019ac04  nop     dword ptr [rax+rax+00h]
0x18019ac09  mov     ebx, eax
0x18019ac0b  jmp     short loc_18019AC37
0x18019ac0d  test    ebp, ebp
0x18019ac0f  jnz     short loc_18019AC37
0x18019ac11  mov     rsi, [rdi]
0x18019ac14  test    rsi, rsi
0x18019ac17  jz      short loc_18019AC37
0x18019ac19  call    cs:__imp_GetProcessHeap
0x18019ac20  nop     dword ptr [rax+rax+00h]
0x18019ac25  mov     rcx, rax; void *
0x18019ac28  mov     r8, rsi; void *
0x18019ac2b  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x18019ac30  mov     qword ptr [rdi], 0
0x18019ac37  mov     eax, ebx
0x18019ac39  jmp     short loc_18019AC47
0x18019ac3b  mov     qword ptr [rdi], 0
0x18019ac42  mov     eax, 8
0x18019ac47  mov     rbx, [rsp+68h+arg_0]
0x18019ac4c  mov     rbp, [rsp+68h+arg_8]
0x18019ac51  add     rsp, 40h
0x18019ac55  pop     r15
0x18019ac57  pop     r14
0x18019ac59  pop     r12
0x18019ac5b  pop     rdi
0x18019ac5c  pop     rsi
0x18019ac5d  retn
```
