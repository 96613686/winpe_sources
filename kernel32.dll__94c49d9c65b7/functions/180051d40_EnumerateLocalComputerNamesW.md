# EnumerateLocalComputerNamesW

- ea: `0x180051d40`
- end: `0x180051f12`
- name: `EnumerateLocalComputerNamesW`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068ae0`

## callees

- `0x180051d40`
- `0x180051f18`
- `0x18007a7d1`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180051e76`
- `ntdll!RtlFreeHeap` at `0x180051e76`
- `ntdll!RtlAllocateHeap` at `0x180051dc5`
- `ntdll!RtlAllocateHeap` at `0x180051dc5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180051daa`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180051daa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051de7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051ec2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051de7`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180051ec2`

## pseudocode

```c
__int64 __fastcall EnumerateLocalComputerNamesW(unsigned int a1, __int64 a2, void *a3, DWORD *a4)
{
  __int64 v6; // rcx
  ULONG *GlobalData; // rax
  WCHAR *Heap; // rax
  WCHAR *v9; // r14
  ULONG LastErrorValue; // ebx
  DWORD v11; // ecx
  DWORD v12; // eax
  _DWORD v14[4]; // [rsp+20h] [rbp-10h] BYREF
  DWORD nSize; // [rsp+58h] [rbp+28h] BYREF

  nSize = 0;
  if ( !(_DWORD)a2 && a1 <= 2 )
  {
    if ( a1 )
    {
      v6 = a1 - 1;
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 == 1 && a4 && (a3 || !*a4) )
        {
          nSize = *a4;
          GlobalData = (ULONG *)KernelBaseGetGlobalData(v6, a2, a3, a4);
          Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * *a4);
          v9 = Heap;
          if ( Heap )
          {
            if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, Heap, &nSize)
              || (LastErrorValue = NtCurrentTeb()->LastErrorValue) == 0 )
            {
              v14[0] = *a4 - nSize - 1;
              LastErrorValue = BaseEnumAltDnsFQHostnames(&v9[nSize + 1], v14);
              v11 = nSize + v14[0] + 1;
              *a4 = v11;
              if ( !LastErrorValue )
                memcpy_0(a3, v9, 2LL * (v11 + 1));
            }
            else if ( LastErrorValue == 234 )
            {
              v14[0] = 0;
              LastErrorValue = BaseEnumAltDnsFQHostnames(0, v14);
              if ( !LastErrorValue )
                LastErrorValue = 234;
              *a4 = v14[0] + nSize;
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
          }
          else
          {
            return 8;
          }
          return LastErrorValue;
        }
      }
      else if ( a4 && (a3 || !*a4) )
      {
        return (unsigned int)BaseEnumAltDnsFQHostnames(a3, a4);
      }
    }
    else if ( a4 )
    {
      v12 = *a4 - 1;
      if ( !*a4 )
        v12 = 0;
      nSize = v12;
      if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, (LPWSTR)a3, &nSize) )
      {
        if ( a3 )
        {
          LastErrorValue = 0;
          *((_WORD *)a3 + nSize + 1) = 0;
        }
        else
        {
          LastErrorValue = 31;
        }
      }
      else
      {
        LastErrorValue = NtCurrentTeb()->LastErrorValue;
      }
      *a4 = nSize + 1;
      return LastErrorValue;
    }
    return 87;
  }
  return 87;
}

```

## disassembly

```asm
0x180051d40  mov     [rsp-18h+arg_0], rbx
0x180051d45  mov     [rsp-18h+arg_10], rsi
0x180051d4a  push    rbp
0x180051d4b  push    rdi
0x180051d4c  push    r14
0x180051d4e  mov     rbp, rsp
0x180051d51  sub     rsp, 30h
0x180051d55  mov     [rbp+nSize], 0
0x180051d5c  mov     rdi, r9
0x180051d5f  mov     rsi, r8
0x180051d62  test    edx, edx
0x180051d64  jnz     loc_180051EFA
0x180051d6a  cmp     ecx, 2
0x180051d6d  ja      loc_180051EFA
0x180051d73  test    ecx, ecx
0x180051d75  jz      loc_180051E9C
0x180051d7b  sub     ecx, 1
0x180051d7e  jz      loc_180051E7E
0x180051d84  cmp     ecx, 1
0x180051d87  jnz     loc_180051EA1
0x180051d8d  test    r9, r9
0x180051d90  jz      loc_180051EA1
0x180051d96  test    r8, r8
0x180051d99  jnz     short loc_180051DA4
0x180051d9b  cmp     [r9], edx
0x180051d9e  ja      loc_180051EA1
0x180051da4  mov     eax, [r9]
0x180051da7  mov     [rbp+nSize], eax
0x180051daa  call    cs:__imp_KernelBaseGetGlobalData
0x180051db0  mov     rcx, gs:60h
0x180051db9  mov     r8d, [rdi]
0x180051dbc  add     r8, r8; Size
0x180051dbf  mov     edx, [rax]; Flags
0x180051dc1  mov     rcx, [rcx+30h]; HeapHandle
0x180051dc5  call    cs:__imp_RtlAllocateHeap
0x180051dcb  mov     r14, rax
0x180051dce  test    rax, rax
0x180051dd1  jnz     short loc_180051DDB
0x180051dd3  lea     ebx, [rax+8]
0x180051dd6  jmp     loc_180051EF6
0x180051ddb  lea     r8, [rbp+nSize]; nSize
0x180051ddf  mov     rdx, r14; lpBuffer
0x180051de2  mov     ecx, 7; NameType
0x180051de7  call    cs:__imp_GetComputerNameExW
0x180051ded  test    eax, eax
0x180051def  jnz     short loc_180051E25
0x180051df1  mov     ebx, gs:68h
0x180051df9  test    ebx, ebx
0x180051dfb  jz      short loc_180051E25
0x180051dfd  mov     esi, 0EAh
0x180051e02  cmp     ebx, esi
0x180051e04  jnz     short loc_180051E64
0x180051e06  lea     rdx, [rbp+var_10]
0x180051e0a  mov     [rbp+var_10], eax
0x180051e0d  xor     ecx, ecx
0x180051e0f  call    BaseEnumAltDnsFQHostnames
0x180051e14  mov     ecx, [rbp+nSize]
0x180051e17  test    eax, eax
0x180051e19  mov     ebx, eax
0x180051e1b  cmovz   ebx, esi
0x180051e1e  add     ecx, [rbp+var_10]
0x180051e21  mov     [rdi], ecx
0x180051e23  jmp     short loc_180051E64
0x180051e25  mov     eax, [rdi]
0x180051e27  lea     rdx, [rbp+var_10]
0x180051e2b  sub     eax, [rbp+nSize]
0x180051e2e  dec     eax
0x180051e30  mov     [rbp+var_10], eax
0x180051e33  mov     eax, [rbp+nSize]
0x180051e36  inc     rax
0x180051e39  lea     rcx, [r14+rax*2]
0x180051e3d  call    BaseEnumAltDnsFQHostnames
0x180051e42  mov     ecx, [rbp+var_10]
0x180051e45  mov     ebx, eax
0x180051e47  inc     ecx
0x180051e49  add     ecx, [rbp+nSize]
0x180051e4c  mov     [rdi], ecx
0x180051e4e  test    eax, eax
0x180051e50  jnz     short loc_180051E64
0x180051e52  lea     r8d, [rcx+1]
0x180051e56  mov     rdx, r14; Src
0x180051e59  add     r8, r8; Size
0x180051e5c  mov     rcx, rsi; void *
0x180051e5f  call    memcpy_0
0x180051e64  mov     rcx, gs:60h
0x180051e6d  mov     r8, r14; P
0x180051e70  xor     edx, edx; Flags
0x180051e72  mov     rcx, [rcx+30h]; HeapHandle
0x180051e76  call    cs:__imp_RtlFreeHeap
0x180051e7c  jmp     short loc_180051EF6
0x180051e7e  test    rdi, rdi
0x180051e81  jz      short loc_180051EA1
0x180051e83  test    rsi, rsi
0x180051e86  jnz     short loc_180051E8D
0x180051e88  cmp     [r9], esi
0x180051e8b  ja      short loc_180051EA1
0x180051e8d  mov     rdx, rdi
0x180051e90  mov     rcx, rsi
0x180051e93  call    BaseEnumAltDnsFQHostnames
0x180051e98  mov     ebx, eax
0x180051e9a  jmp     short loc_180051EF6
0x180051e9c  test    rdi, rdi
0x180051e9f  jnz     short loc_180051EA8
0x180051ea1  mov     ebx, 57h ; 'W'
0x180051ea6  jmp     short loc_180051EF6
0x180051ea8  mov     ecx, [r9]
0x180051eab  lea     r8, [rbp+nSize]; nSize
0x180051eaf  test    ecx, ecx
0x180051eb1  mov     rdx, rsi; lpBuffer
0x180051eb4  lea     eax, [rcx-1]
0x180051eb7  cmovz   eax, ecx
0x180051eba  mov     ecx, 7; NameType
0x180051ebf  mov     [rbp+nSize], eax
0x180051ec2  call    cs:__imp_GetComputerNameExW
0x180051ec8  test    eax, eax
0x180051eca  jnz     short loc_180051ED6
0x180051ecc  mov     ebx, gs:68h
0x180051ed4  jmp     short loc_180051EEF
0x180051ed6  test    rsi, rsi
0x180051ed9  jz      short loc_180051EEA
0x180051edb  mov     ecx, [rbp+nSize]
0x180051ede  xor     ebx, ebx
0x180051ee0  inc     ecx
0x180051ee2  xor     eax, eax
0x180051ee4  mov     [rsi+rcx*2], ax
0x180051ee8  jmp     short loc_180051EEF
0x180051eea  mov     ebx, 1Fh
0x180051eef  mov     eax, [rbp+nSize]
0x180051ef2  inc     eax
0x180051ef4  mov     [rdi], eax
0x180051ef6  mov     eax, ebx
0x180051ef8  jmp     short loc_180051EFF
0x180051efa  mov     eax, 57h ; 'W'
0x180051eff  mov     rbx, [rsp+30h+arg_0]
0x180051f04  mov     rsi, [rsp+30h+arg_10]
0x180051f09  add     rsp, 30h
0x180051f0d  pop     r14
0x180051f0f  pop     rdi
0x180051f10  pop     rbp
0x180051f11  retn
```
