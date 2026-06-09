# EnumerateLocalComputerNamesW

- ea: `0x180057540`
- end: `0x180057731`
- name: `EnumerateLocalComputerNamesW`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006fc00`

## callees

- `0x180057540`
- `0x180057738`
- `0x180082751`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180057688`
- `ntdll!RtlFreeHeap` at `0x180057688`
- `ntdll!RtlAllocateHeap` at `0x1800575cb`
- `ntdll!RtlAllocateHeap` at `0x1800575cb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800575aa`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800575aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800575f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800576da`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800575f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800576da`

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
0x180057540  mov     [rsp-18h+arg_0], rbx
0x180057545  mov     [rsp-18h+arg_10], rsi
0x18005754a  push    rbp
0x18005754b  push    rdi
0x18005754c  push    r14
0x18005754e  mov     rbp, rsp
0x180057551  sub     rsp, 30h
0x180057555  mov     [rbp+nSize], 0
0x18005755c  mov     rdi, r9
0x18005755f  mov     rsi, r8
0x180057562  test    edx, edx
0x180057564  jnz     loc_180057718
0x18005756a  cmp     ecx, 2
0x18005756d  ja      loc_180057718
0x180057573  test    ecx, ecx
0x180057575  jz      loc_1800576B4
0x18005757b  sub     ecx, 1
0x18005757e  jz      loc_180057696
0x180057584  cmp     ecx, 1
0x180057587  jnz     loc_1800576B9
0x18005758d  test    r9, r9
0x180057590  jz      loc_1800576B9
0x180057596  test    r8, r8
0x180057599  jnz     short loc_1800575A4
0x18005759b  cmp     [r9], edx
0x18005759e  ja      loc_1800576B9
0x1800575a4  mov     eax, [r9]
0x1800575a7  mov     [rbp+nSize], eax
0x1800575aa  call    cs:__imp_KernelBaseGetGlobalData
0x1800575b1  nop     dword ptr [rax+rax+00h]
0x1800575b6  mov     rcx, gs:60h
0x1800575bf  mov     r8d, [rdi]
0x1800575c2  add     r8, r8; Size
0x1800575c5  mov     edx, [rax]; Flags
0x1800575c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800575cb  call    cs:__imp_RtlAllocateHeap
0x1800575d2  nop     dword ptr [rax+rax+00h]
0x1800575d7  mov     r14, rax
0x1800575da  test    rax, rax
0x1800575dd  jnz     short loc_1800575E7
0x1800575df  lea     ebx, [rax+8]
0x1800575e2  jmp     loc_180057714
0x1800575e7  lea     r8, [rbp+nSize]; nSize
0x1800575eb  mov     rdx, r14; lpBuffer
0x1800575ee  mov     ecx, 7; NameType
0x1800575f3  call    cs:__imp_GetComputerNameExW
0x1800575fa  nop     dword ptr [rax+rax+00h]
0x1800575ff  test    eax, eax
0x180057601  jnz     short loc_180057637
0x180057603  mov     ebx, gs:68h
0x18005760b  test    ebx, ebx
0x18005760d  jz      short loc_180057637
0x18005760f  mov     esi, 0EAh
0x180057614  cmp     ebx, esi
0x180057616  jnz     short loc_180057676
0x180057618  lea     rdx, [rbp+var_10]
0x18005761c  mov     [rbp+var_10], eax
0x18005761f  xor     ecx, ecx
0x180057621  call    BaseEnumAltDnsFQHostnames
0x180057626  mov     ecx, [rbp+nSize]
0x180057629  test    eax, eax
0x18005762b  mov     ebx, eax
0x18005762d  cmovz   ebx, esi
0x180057630  add     ecx, [rbp+var_10]
0x180057633  mov     [rdi], ecx
0x180057635  jmp     short loc_180057676
0x180057637  mov     eax, [rdi]
0x180057639  lea     rdx, [rbp+var_10]
0x18005763d  sub     eax, [rbp+nSize]
0x180057640  dec     eax
0x180057642  mov     [rbp+var_10], eax
0x180057645  mov     eax, [rbp+nSize]
0x180057648  inc     rax
0x18005764b  lea     rcx, [r14+rax*2]
0x18005764f  call    BaseEnumAltDnsFQHostnames
0x180057654  mov     ecx, [rbp+var_10]
0x180057657  mov     ebx, eax
0x180057659  inc     ecx
0x18005765b  add     ecx, [rbp+nSize]
0x18005765e  mov     [rdi], ecx
0x180057660  test    eax, eax
0x180057662  jnz     short loc_180057676
0x180057664  lea     r8d, [rcx+1]
0x180057668  mov     rdx, r14; Src
0x18005766b  add     r8, r8; Size
0x18005766e  mov     rcx, rsi; void *
0x180057671  call    memcpy_0
0x180057676  mov     rcx, gs:60h
0x18005767f  mov     r8, r14; P
0x180057682  xor     edx, edx; Flags
0x180057684  mov     rcx, [rcx+30h]; HeapHandle
0x180057688  call    cs:__imp_RtlFreeHeap
0x18005768f  nop     dword ptr [rax+rax+00h]
0x180057694  jmp     short loc_180057714
0x180057696  test    rdi, rdi
0x180057699  jz      short loc_1800576B9
0x18005769b  test    rsi, rsi
0x18005769e  jnz     short loc_1800576A5
0x1800576a0  cmp     [r9], esi
0x1800576a3  ja      short loc_1800576B9
0x1800576a5  mov     rdx, rdi
0x1800576a8  mov     rcx, rsi
0x1800576ab  call    BaseEnumAltDnsFQHostnames
0x1800576b0  mov     ebx, eax
0x1800576b2  jmp     short loc_180057714
0x1800576b4  test    rdi, rdi
0x1800576b7  jnz     short loc_1800576C0
0x1800576b9  mov     ebx, 57h ; 'W'
0x1800576be  jmp     short loc_180057714
0x1800576c0  mov     ecx, [r9]
0x1800576c3  lea     r8, [rbp+nSize]; nSize
0x1800576c7  test    ecx, ecx
0x1800576c9  mov     rdx, rsi; lpBuffer
0x1800576cc  lea     eax, [rcx-1]
0x1800576cf  cmovz   eax, ecx
0x1800576d2  mov     ecx, 7; NameType
0x1800576d7  mov     [rbp+nSize], eax
0x1800576da  call    cs:__imp_GetComputerNameExW
0x1800576e1  nop     dword ptr [rax+rax+00h]
0x1800576e6  test    eax, eax
0x1800576e8  jnz     short loc_1800576F4
0x1800576ea  mov     ebx, gs:68h
0x1800576f2  jmp     short loc_18005770D
0x1800576f4  test    rsi, rsi
0x1800576f7  jz      short loc_180057708
0x1800576f9  mov     ecx, [rbp+nSize]
0x1800576fc  xor     ebx, ebx
0x1800576fe  inc     ecx
0x180057700  xor     eax, eax
0x180057702  mov     [rsi+rcx*2], ax
0x180057706  jmp     short loc_18005770D
0x180057708  mov     ebx, 1Fh
0x18005770d  mov     eax, [rbp+nSize]
0x180057710  inc     eax
0x180057712  mov     [rdi], eax
0x180057714  mov     eax, ebx
0x180057716  jmp     short loc_18005771D
0x180057718  mov     eax, 57h ; 'W'
0x18005771d  mov     rbx, [rsp+30h+arg_0]
0x180057722  mov     rsi, [rsp+30h+arg_10]
0x180057727  add     rsp, 30h
0x18005772b  pop     r14
0x18005772d  pop     rdi
0x18005772e  pop     rbp
0x18005772f  retn
```
