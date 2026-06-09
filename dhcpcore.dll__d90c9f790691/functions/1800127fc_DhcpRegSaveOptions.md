# DhcpRegSaveOptions

- ea: `0x1800127fc`
- end: `0x180012a16`
- name: `DhcpRegSaveOptions`
- size: `538`
- prototype: `LSTATUS __fastcall(_QWORD *, void *, HKEY, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180015fec`
- `0x18001c240`
- `0x1800227ac`

## callees

- `0x180006440`
- `0x18000c4b8`
- `0x1800127fc`
- `0x180012a1c`
- `0x180047e3c`
- `0x18004d4f8`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800129f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800129df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800129df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012921`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180012921`

## pseudocode

```c
LSTATUS __fastcall DhcpRegSaveOptions(_QWORD *a1, void *a2, HKEY a3, __int64 a4, unsigned int a5, int a6)
{
  _QWORD *v8; // rbx
  int v9; // esi
  DWORD cbData; // r15d
  unsigned int v11; // edi
  _QWORD *v12; // rbp
  const char *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  _DWORD *v17; // rax
  _DWORD *v18; // rcx
  _QWORD *v19; // rsi
  BYTE *lpData; // r12
  _QWORD *v21; // rdi
  _DWORD *v22; // rbp
  char *v23; // rbx
  LSTATUS v24; // ebx

  DhcpRegClearOptDefsEx(a1, a4, a5, a2);
  v8 = (_QWORD *)*a1;
  v9 = 0;
  cbData = 0;
  v11 = 0;
  while ( v8 != a1 )
  {
    v12 = (_QWORD *)*v8;
    if ( *((_DWORD *)v8 + 8) == a5 && v8[3] == a4 )
    {
      v9 = DhcpRegSaveOption(v8, a2, a6);
      if ( v9 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v13 = "Vendor";
          if ( !*((_DWORD *)v8 + 5) )
            v13 = "NotVendor";
          WPP_SF_lsD(
            (_DWORD)v13,
            37,
            (unsigned int)WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids,
            *((_DWORD *)v8 + 4),
            (__int64)v13,
            v9);
        }
      }
    }
    v14 = *((_DWORD *)v8 + 8);
    if ( v14 + 20 < v14 )
      return 87;
    v15 = *((_DWORD *)v8 + 14) + v14 + 20;
    if ( v15 < *((_DWORD *)v8 + 14) )
      return 87;
    cbData += (v15 + 3) & 0xFFFFFFFC;
    if ( cbData < v15 )
      return 87;
    v8 = v12;
    ++v11;
  }
  if ( v9 && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_Dd(1025, 38, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v11, v9);
  if ( !v11 )
    return RegDeleteValueW(a3, L"DhcpInterfaceOptions");
  v17 = DhcpAlloc(cbData);
  v18 = v17;
  if ( !v17 )
    return 8;
  v19 = (_QWORD *)*a1;
  lpData = (BYTE *)v17;
  while ( v19 != a1 )
  {
    v21 = v19;
    v19 = (_QWORD *)*v19;
    v22 = v18 + 5;
    *v18 = *((_DWORD *)v21 + 4);
    v18[1] = *((_DWORD *)v21 + 8);
    v18[2] = *((_DWORD *)v21 + 14);
    v18[3] = *((_DWORD *)v21 + 5);
    v18[4] = *((_DWORD *)v21 + 10);
    if ( *((_DWORD *)v21 + 8) )
    {
      memcpy_0(v18 + 5, (const void *)v21[3], *((unsigned int *)v21 + 8));
      v23 = (char *)v22 + *((unsigned int *)v21 + 8);
    }
    else
    {
      v23 = (char *)(v18 + 5);
    }
    if ( *((_DWORD *)v21 + 14) )
    {
      memcpy_0(v23, (const void *)v21[6], *((unsigned int *)v21 + 14));
      v23 += *((unsigned int *)v21 + 14);
    }
    v18 = (_DWORD *)((unsigned __int64)(v23 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
  }
  v24 = RegSetValueExW(a3, L"DhcpInterfaceOptions", 0, 3u, lpData, cbData);
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, lpData);
  return v24;
}

```

## disassembly

```asm
0x1800127fc  mov     [rsp+arg_0], rbx
0x180012801  mov     [rsp+hKey], r8
0x180012806  mov     [rsp+arg_8], rdx
0x18001280b  push    rbp
0x18001280c  push    rsi
0x18001280d  push    rdi
0x18001280e  push    r12
0x180012810  push    r13
0x180012812  push    r14
0x180012814  push    r15
0x180012816  sub     rsp, 30h
0x18001281a  mov     r13d, [rsp+68h+arg_20]
0x180012822  mov     r12, r9
0x180012825  mov     r9, rdx
0x180012828  mov     r8d, r13d
0x18001282b  mov     rdx, r12
0x18001282e  mov     r14, rcx
0x180012831  call    DhcpRegClearOptDefsEx
0x180012836  mov     rbx, [r14]
0x180012839  xor     esi, esi
0x18001283b  xor     r15d, r15d
0x18001283e  xor     edi, edi
0x180012840  cmp     rbx, r14
0x180012843  jz      loc_1800128E4
0x180012849  mov     rbp, [rbx]
0x18001284c  cmp     [rbx+20h], r13d
0x180012850  jnz     short loc_1800128B0
0x180012852  cmp     [rbx+18h], r12
0x180012856  jnz     short loc_1800128B0
0x180012858  mov     r8d, [rsp+68h+arg_28]
0x180012860  mov     rcx, rbx
0x180012863  mov     rdx, [rsp+68h+arg_8]
0x180012868  call    DhcpRegSaveOption
0x18001286d  mov     esi, eax
0x18001286f  test    eax, eax
0x180012871  jz      short loc_1800128B0
0x180012873  test    byte ptr cs:xmmword_1800616A0, 2
0x18001287a  jz      short loc_1800128B0
0x18001287c  cmp     dword ptr [rbx+14h], 0
0x180012880  lea     rax, aNotvendor; "NotVendor"
0x180012887  mov     r9d, [rbx+10h]
0x18001288b  lea     rcx, aVendor_1; "Vendor"
0x180012892  cmovz   rcx, rax
0x180012896  mov     [rsp+68h+cbData], esi
0x18001289a  mov     edx, 25h ; '%'
0x18001289f  mov     [rsp+68h+lpData], rcx
0x1800128a4  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800128ab  call    WPP_SF_lsD
0x1800128b0  mov     eax, [rbx+20h]
0x1800128b3  lea     ecx, [rax+14h]
0x1800128b6  cmp     ecx, eax
0x1800128b8  jb      short loc_1800128DA
0x1800128ba  add     ecx, [rbx+38h]
0x1800128bd  cmp     ecx, [rbx+38h]
0x1800128c0  jb      short loc_1800128DA
0x1800128c2  lea     eax, [rcx+3]
0x1800128c5  and     eax, 0FFFFFFFCh
0x1800128c8  add     r15d, eax
0x1800128cb  cmp     r15d, ecx
0x1800128ce  jb      short loc_1800128DA
0x1800128d0  mov     rbx, rbp
0x1800128d3  inc     edi
0x1800128d5  jmp     loc_180012840
0x1800128da  mov     eax, 57h ; 'W'
0x1800128df  jmp     loc_180012A01
0x1800128e4  test    esi, esi
0x1800128e6  jz      short loc_18001290E
0x1800128e8  test    byte ptr cs:xmmword_1800616A0, 2
0x1800128ef  jz      short loc_18001290E
0x1800128f1  mov     edx, 26h ; '&'
0x1800128f6  mov     dword ptr [rsp+68h+lpData], esi
0x1800128fa  mov     ecx, 401h
0x1800128ff  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x180012906  mov     r9d, edi
0x180012909  call    WPP_SF_Dd
0x18001290e  test    edi, edi
0x180012910  jnz     short loc_18001292C
0x180012912  mov     rcx, [rsp+68h+hKey]; hKey
0x18001291a  lea     rdx, aDhcpinterfaceo; "DhcpInterfaceOptions"
0x180012921  call    cs:__imp_RegDeleteValueW
0x180012927  jmp     loc_180012A01
0x18001292c  mov     ecx, r15d
0x18001292f  call    DhcpAlloc
0x180012934  mov     rcx, rax
0x180012937  test    rax, rax
0x18001293a  jnz     short loc_180012944
0x18001293c  lea     eax, [rcx+8]
0x18001293f  jmp     loc_180012A01
0x180012944  mov     rsi, [r14]
0x180012947  mov     r12, rax
0x18001294a  jmp     short loc_1800129B8
0x18001294c  lea     rdi, [rsi]
0x18001294f  mov     rsi, [rsi]
0x180012952  mov     eax, [rdi+10h]
0x180012955  lea     rbp, [rcx+14h]
0x180012959  mov     [rcx], eax
0x18001295b  mov     eax, [rdi+20h]
0x18001295e  mov     [rcx+4], eax
0x180012961  mov     eax, [rdi+38h]
0x180012964  mov     [rcx+8], eax
0x180012967  mov     eax, [rdi+14h]
0x18001296a  mov     [rcx+0Ch], eax
0x18001296d  mov     eax, [rdi+28h]
0x180012970  mov     [rcx+10h], eax
0x180012973  cmp     dword ptr [rdi+20h], 0
0x180012977  jz      short loc_180012991
0x180012979  mov     r8d, [rdi+20h]; Size
0x18001297d  mov     rcx, rbp; void *
0x180012980  mov     rdx, [rdi+18h]; Src
0x180012984  call    memcpy_0
0x180012989  mov     ebx, [rdi+20h]
0x18001298c  add     rbx, rbp
0x18001298f  jmp     short loc_180012994
0x180012991  mov     rbx, rbp
0x180012994  cmp     dword ptr [rdi+38h], 0
0x180012998  jz      short loc_1800129B0
0x18001299a  mov     r8d, [rdi+38h]; Size
0x18001299e  mov     rcx, rbx; void *
0x1800129a1  mov     rdx, [rdi+30h]; Src
0x1800129a5  call    memcpy_0
0x1800129aa  mov     eax, [rdi+38h]
0x1800129ad  add     rbx, rax
0x1800129b0  lea     rcx, [rbx+3]
0x1800129b4  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800129b8  cmp     rsi, r14
0x1800129bb  jnz     short loc_18001294C
0x1800129bd  mov     rcx, [rsp+68h+hKey]; hKey
0x1800129c5  lea     rdx, aDhcpinterfaceo; "DhcpInterfaceOptions"
0x1800129cc  mov     [rsp+68h+cbData], r15d; cbData
0x1800129d1  mov     r9d, 3; dwType
0x1800129d7  xor     r8d, r8d; Reserved
0x1800129da  mov     [rsp+68h+lpData], r12; lpData
0x1800129df  call    cs:__imp_RegSetValueExW
0x1800129e5  mov     rcx, gs:60h
0x1800129ee  mov     r8, r12; lpMem
0x1800129f1  xor     edx, edx; dwFlags
0x1800129f3  mov     ebx, eax
0x1800129f5  mov     rcx, [rcx+30h]; hHeap
0x1800129f9  call    cs:__imp_HeapFree
0x1800129ff  mov     eax, ebx
0x180012a01  mov     rbx, [rsp+68h+arg_0]
0x180012a06  add     rsp, 30h
0x180012a0a  pop     r15
0x180012a0c  pop     r14
0x180012a0e  pop     r13
0x180012a10  pop     r12
0x180012a12  pop     rdi
0x180012a13  pop     rsi
0x180012a14  pop     rbp
0x180012a15  retn
```
