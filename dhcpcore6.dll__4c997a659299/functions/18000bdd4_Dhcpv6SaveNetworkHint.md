# Dhcpv6SaveNetworkHint

- ea: `0x18000bdd4`
- end: `0x18000bf08`
- name: `Dhcpv6SaveNetworkHint`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008a70`
- `0x180011400`

## callees

- `0x18000bdd4`
- `0x18000bf10`
- `0x18000c740`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000be90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000be90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bebc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bebc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000be4c`

## pseudocode

```c
__int64 __fastcall Dhcpv6SaveNetworkHint(RTL_SRWLOCK *a1)
{
  unsigned int v1; // ebp
  BYTE *lpData; // rsi
  HKEY Ptr; // rcx
  int v6; // [rsp+68h] [rbp+10h] BYREF
  BYTE *v7; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  v7 = 0;
  v6 = 0;
  if ( *(_DWORD *)&Dhcpv6GlobalUseNetworkHint )
  {
    GetNetworkHint(&a1[3], &v7, &v6, 0);
    AcquireSRWLockExclusive(a1 + 76);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 101, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, a1[7].Ptr);
    if ( a1[1119].Ptr )
      DhcpFree(&a1[1119].Ptr);
    lpData = v7;
    a1[1119].Ptr = v7;
    ReleaseSRWLockExclusive(a1 + 76);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 102, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, a1[7].Ptr);
    Ptr = (HKEY)a1[81].Ptr;
    if ( lpData )
      return (unsigned int)RegSetValueExW(Ptr, L"DhcpV6NetworkHint", 0, 1u, lpData, 2 * v6);
    else
      RegDeleteValueW(Ptr, L"DhcpV6NetworkHint");
  }
  return v1;
}

```

## disassembly

```asm
0x18000bdd4  mov     rax, rsp
0x18000bdd7  mov     [rax+8], rbx
0x18000bddb  push    rbp
0x18000bddc  push    rsi
0x18000bddd  push    rdi
0x18000bdde  push    r14
0x18000bde0  push    r15
0x18000bde2  sub     rsp, 30h
0x18000bde6  xor     ebp, ebp
0x18000bde8  mov     rbx, rcx
0x18000bdeb  cmp     cs:Dhcpv6GlobalUseNetworkHint, ebp
0x18000bdf1  mov     [rax+18h], rbp
0x18000bdf5  mov     [rax+10h], ebp
0x18000bdf8  jz      loc_18000BE9E
0x18000bdfe  add     rcx, 18h
0x18000be02  lea     r8, [rax+10h]
0x18000be06  xor     r9d, r9d
0x18000be09  lea     rdx, [rax+18h]
0x18000be0d  call    GetNetworkHint
0x18000be12  lea     r15, [rbx+260h]
0x18000be19  mov     rcx, r15; SRWLock
0x18000be1c  call    cs:__imp_AcquireSRWLockExclusive
0x18000be23  nop     dword ptr [rax+rax+00h]
0x18000be28  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000be2f  jnz     loc_18000BECA
0x18000be35  lea     rdi, [rbx+22F8h]
0x18000be3c  cmp     [rdi], rbp
0x18000be3f  jnz     short loc_18000BEB2
0x18000be41  mov     rsi, [rsp+58h+arg_10]
0x18000be46  mov     rcx, r15; SRWLock
0x18000be49  mov     [rdi], rsi
0x18000be4c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000be53  nop     dword ptr [rax+rax+00h]
0x18000be58  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000be5f  jnz     loc_18000BEE9
0x18000be65  mov     rcx, [rbx+288h]; hKey
0x18000be6c  lea     rdx, aDhcpv6networkh; "DhcpV6NetworkHint"
0x18000be73  test    rsi, rsi
0x18000be76  jz      short loc_18000BEBC
0x18000be78  mov     eax, [rsp+58h+arg_8]
0x18000be7c  mov     r9d, 1; dwType
0x18000be82  add     eax, eax
0x18000be84  xor     r8d, r8d; Reserved
0x18000be87  mov     [rsp+58h+cbData], eax; cbData
0x18000be8b  mov     [rsp+58h+lpData], rsi; lpData
0x18000be90  call    cs:__imp_RegSetValueExW
0x18000be97  nop     dword ptr [rax+rax+00h]
0x18000be9c  mov     ebp, eax
0x18000be9e  mov     rbx, [rsp+58h+arg_0]
0x18000bea3  mov     eax, ebp
0x18000bea5  add     rsp, 30h
0x18000bea9  pop     r15
0x18000beab  pop     r14
0x18000bead  pop     rdi
0x18000beae  pop     rsi
0x18000beaf  pop     rbp
0x18000beb0  retn
0x18000beb2  mov     rcx, rdi
0x18000beb5  call    DhcpFree
0x18000beba  jmp     short loc_18000BE41
0x18000bebc  call    cs:__imp_RegDeleteValueW
0x18000bec3  nop     dword ptr [rax+rax+00h]
0x18000bec8  jmp     short loc_18000BE9E
0x18000beca  mov     r9, [rbx+38h]
0x18000bece  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000bed5  mov     edx, 65h ; 'e'
0x18000beda  mov     ecx, 404h
0x18000bedf  call    WPP_SF_S
0x18000bee4  jmp     loc_18000BE35
0x18000bee9  mov     r9, [rbx+38h]
0x18000beed  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000bef4  mov     edx, 66h ; 'f'
0x18000bef9  mov     ecx, 404h
0x18000befe  call    WPP_SF_S
0x18000bf03  jmp     loc_18000BE65
```
