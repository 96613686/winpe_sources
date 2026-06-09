# CLONE_INSTALLED_PROGRAMS::GetNextElement(CLONE_SOFTWARE_ELEMENT * *)

- ea: `0x1800240e0`
- end: `0x1800242f9`
- name: `?GetNextElement@CLONE_INSTALLED_PROGRAMS@@UEAAKPEAPEAVCLONE_SOFTWARE_ELEMENT@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(CLONE_INSTALLED_PROGRAMS *this, struct CLONE_SOFTWARE_ELEMENT **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180003308`
- `0x180023afc`
- `0x1800240e0`
- `0x180024548`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800241f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800241f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002414c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002414c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024193`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024193`
- `ntdll!iswspace` at `0x18002423e`
- `ntdll!iswspace` at `0x18002423e`

## pseudocode

```c
__int64 __fastcall CLONE_INSTALLED_PROGRAMS::GetNextElement(
        CLONE_INSTALLED_PROGRAMS *this,
        struct CLONE_SOFTWARE_ELEMENT **a2)
{
  struct CLONE_SOFTWARE_ELEMENT *v4; // rdi
  HKEY *v5; // r14
  unsigned int v6; // edx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS ValueW; // eax
  __int64 v10; // rax
  DWORD i; // ecx
  struct CLONE_SOFTWARE_ELEMENT *v12; // rax
  DWORD cchName; // [rsp+40h] [rbp-468h] BYREF
  unsigned int v15; // [rsp+44h] [rbp-464h]
  struct CLONE_SOFTWARE_ELEMENT *v16; // [rsp+48h] [rbp-460h]
  _WORD pvData[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR Name[264]; // [rsp+260h] [rbp-248h] BYREF

  cchName = 0;
  v4 = 0;
  v16 = 0;
  *a2 = 0;
  v5 = (HKEY *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    do
    {
      while ( 1 )
      {
LABEL_4:
        cchName = 260;
        v8 = RegEnumKeyExW(*v5, *((_DWORD *)this + 4), Name, &cchName, 0, 0, 0, 0);
        v7 = v8;
        v15 = v8;
        if ( v8 )
        {
          if ( v8 != 259 )
            goto LABEL_27;
          v7 = 0;
          goto LABEL_7;
        }
        ++*((_DWORD *)this + 4);
        cchName = 260;
        ValueW = RegGetValueW(*v5, Name, L"DisplayName", 2u, 0, pvData, &cchName);
        v7 = ValueW;
        v15 = ValueW;
        if ( !ValueW )
          break;
        if ( ValueW != 2 )
          goto LABEL_27;
        v15 = 0;
      }
      v10 = -1;
      do
        ++v10;
      while ( pvData[v10] );
      cchName = v10;
      for ( i = v10; (_DWORD)v10 && iswspace(pvData[i - 1]); LODWORD(v10) = i )
      {
        i = cchName - 1;
        cchName = i;
      }
    }
    while ( !cchName || !pvData[0] );
    v12 = (struct CLONE_SOFTWARE_ELEMENT *)operator new(0x10u);
    v4 = v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = 0;
      *((_DWORD *)v12 + 2) = 0;
    }
    else
    {
      v4 = 0;
    }
    v16 = v4;
    if ( !v4 )
    {
      v7 = 14;
LABEL_7:
      v15 = v7;
      goto LABEL_27;
    }
    v7 = CLONE_SOFTWARE_ELEMENT::Initialize(v4, pvData, *((_DWORD *)this + 5) != 0);
    v15 = v7;
    if ( !v7 )
    {
      *a2 = v4;
      v4 = 0;
      v16 = 0;
    }
  }
  else
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, off_18002F368[*((int *)this + 5)], 0, 0x20019u, (PHKEY)this + 1);
    v15 = v7;
    if ( !v7 )
    {
      *((_DWORD *)this + 4) = 0;
      goto LABEL_4;
    }
  }
LABEL_27:
  if ( v4 )
    CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(v4, v6);
  return v7;
}

```

## disassembly

```asm
0x1800240e0  mov     [rsp+arg_10], rbx
0x1800240e5  push    rsi
0x1800240e6  push    rdi
0x1800240e7  push    r12
0x1800240e9  push    r14
0x1800240eb  push    r15
0x1800240ed  sub     rsp, 480h
0x1800240f4  mov     rax, cs:__security_cookie
0x1800240fb  xor     rax, rsp
0x1800240fe  mov     [rsp+4A8h+var_38], rax
0x180024106  mov     r15, rdx
0x180024109  mov     rsi, rcx
0x18002410c  xor     r12d, r12d
0x18002410f  mov     [rsp+4A8h+cchName], r12d
0x180024114  mov     edi, r12d
0x180024117  mov     [rsp+4A8h+var_460], r12
0x18002411c  mov     [rdx], r12
0x18002411f  lea     r14, [rcx+8]
0x180024123  cmp     [r14], r12
0x180024126  jnz     short loc_180024164
0x180024128  movsxd  rdx, dword ptr [rcx+14h]
0x18002412c  lea     rax, off_18002F368; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024133  mov     [rsp+4A8h+phkResult], r14; phkResult
0x180024138  mov     r9d, 20019h; samDesired
0x18002413e  xor     r8d, r8d; ulOptions
0x180024141  mov     rdx, [rax+rdx*8]; lpSubKey
0x180024145  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002414c  call    cs:__imp_RegOpenKeyExW
0x180024152  mov     ebx, eax
0x180024154  mov     [rsp+4A8h+var_464], eax
0x180024158  test    eax, eax
0x18002415a  jnz     loc_1800242C2
0x180024160  mov     [rsi+10h], r12d
0x180024164  mov     [rsp+4A8h+cchName], 104h
0x18002416c  mov     [rsp+4A8h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180024171  mov     [rsp+4A8h+lpcchClass], r12; lpcchClass
0x180024176  mov     [rsp+4A8h+lpClass], r12; lpClass
0x18002417b  mov     [rsp+4A8h+phkResult], r12; lpReserved
0x180024180  lea     r9, [rsp+4A8h+cchName]; lpcchName
0x180024185  lea     r8, [rsp+4A8h+Name]; lpName
0x18002418d  mov     edx, [rsi+10h]; dwIndex
0x180024190  mov     rcx, [r14]; hKey
0x180024193  call    cs:__imp_RegEnumKeyExW
0x180024199  mov     ebx, eax
0x18002419b  mov     [rsp+4A8h+var_464], eax
0x18002419f  test    eax, eax
0x1800241a1  jz      short loc_1800241BA
0x1800241a3  cmp     eax, 103h
0x1800241a8  jnz     loc_1800242C2
0x1800241ae  mov     ebx, r12d
0x1800241b1  mov     [rsp+4A8h+var_464], ebx
0x1800241b5  jmp     loc_1800242C2
0x1800241ba  inc     dword ptr [rsi+10h]
0x1800241bd  mov     [rsp+4A8h+cchName], 104h
0x1800241c5  lea     rax, [rsp+4A8h+cchName]
0x1800241ca  mov     [rsp+4A8h+lpcchClass], rax; pcbData
0x1800241cf  lea     rax, [rsp+4A8h+pvData]
0x1800241d4  mov     [rsp+4A8h+lpClass], rax; pvData
0x1800241d9  mov     [rsp+4A8h+phkResult], r12; pdwType
0x1800241de  mov     r9d, 2; dwFlags
0x1800241e4  lea     r8, aDisplayname; "DisplayName"
0x1800241eb  lea     rdx, [rsp+4A8h+Name]; lpSubKey
0x1800241f3  mov     rcx, [r14]; hkey
0x1800241f6  call    cs:__imp_RegGetValueW
0x1800241fc  mov     ebx, eax
0x1800241fe  mov     [rsp+4A8h+var_464], eax
0x180024202  test    eax, eax
0x180024204  jz      short loc_180024219
0x180024206  cmp     eax, 2
0x180024209  jnz     loc_1800242C2
0x18002420f  mov     [rsp+4A8h+var_464], r12d
0x180024214  jmp     loc_180024164
0x180024219  lea     rcx, [rsp+4A8h+pvData]
0x18002421e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024222  inc     rax
0x180024225  cmp     [rcx+rax*2], r12w
0x18002422a  jnz     short loc_180024222
0x18002422c  mov     [rsp+4A8h+cchName], eax
0x180024230  mov     ecx, eax
0x180024232  test    eax, eax
0x180024234  jz      short loc_180024256
0x180024236  lea     eax, [rcx-1]
0x180024239  movzx   ecx, [rsp+rax*2+4A8h+pvData]; C
0x18002423e  call    cs:__imp_iswspace
0x180024244  test    eax, eax
0x180024246  jz      short loc_180024256
0x180024248  mov     ecx, [rsp+4A8h+cchName]
0x18002424c  dec     ecx
0x18002424e  mov     [rsp+4A8h+cchName], ecx
0x180024252  mov     eax, ecx
0x180024254  jmp     short loc_180024232
0x180024256  cmp     [rsp+4A8h+cchName], r12d
0x18002425b  jz      short loc_180024214
0x18002425d  cmp     [rsp+4A8h+pvData], r12w
0x180024263  jz      short loc_180024214
0x180024265  mov     ecx, 10h; Size
0x18002426a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002426f  mov     rdi, rax
0x180024272  test    rax, rax
0x180024275  jz      short loc_180024280
0x180024277  mov     [rax], r12
0x18002427a  mov     [rax+8], r12d
0x18002427e  jmp     short loc_180024283
0x180024280  mov     rdi, r12
0x180024283  mov     [rsp+4A8h+var_460], rdi
0x180024288  test    rdi, rdi
0x18002428b  jnz     short loc_180024295
0x18002428d  lea     ebx, [rdi+0Eh]
0x180024290  jmp     loc_1800241B1
0x180024295  mov     r8d, r12d
0x180024298  cmp     [rsi+14h], r12d
0x18002429c  setnz   r8b
0x1800242a0  lea     rdx, [rsp+4A8h+pvData]
0x1800242a5  mov     rcx, rdi
0x1800242a8  call    ?Initialize@CLONE_SOFTWARE_ELEMENT@@QEAAKPEBGW4CLONE_SOFTWARE_TYPE@@@Z; CLONE_SOFTWARE_ELEMENT::Initialize(ushort const *,CLONE_SOFTWARE_TYPE)
0x1800242ad  mov     ebx, eax
0x1800242af  mov     [rsp+4A8h+var_464], eax
0x1800242b3  test    eax, eax
0x1800242b5  jnz     short loc_1800242C2
0x1800242b7  mov     [r15], rdi
0x1800242ba  mov     rdi, r12
0x1800242bd  mov     [rsp+4A8h+var_460], r12
0x1800242c2  test    rdi, rdi
0x1800242c5  jz      short loc_1800242CF
0x1800242c7  mov     rcx, rdi; this
0x1800242ca  call    ??_GCLONE_SOFTWARE_ELEMENT@@QEAAPEAXI@Z; CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(uint)
0x1800242cf  mov     eax, ebx
0x1800242d1  mov     rcx, [rsp+4A8h+var_38]
0x1800242d9  xor     rcx, rsp; StackCookie
0x1800242dc  call    __security_check_cookie
0x1800242e1  mov     rbx, [rsp+4A8h+arg_10]
0x1800242e9  add     rsp, 480h
0x1800242f0  pop     r15
0x1800242f2  pop     r14
0x1800242f4  pop     r12
0x1800242f6  pop     rdi
0x1800242f7  pop     rsi
0x1800242f8  retn
0x18002c542  push    rbp
0x18002c544  sub     rsp, 40h
0x18002c548  mov     rbp, rdx
0x18002c54b  mov     rcx, [rbp+48h]; this
0x18002c54f  test    rcx, rcx
0x18002c552  jz      short loc_18002C55A
0x18002c554  call    ??_GCLONE_SOFTWARE_ELEMENT@@QEAAPEAXI@Z; CLONE_SOFTWARE_ELEMENT::`scalar deleting destructor'(uint)
0x18002c559  nop
0x18002c55a  add     rsp, 40h
0x18002c55e  pop     rbp
0x18002c55f  retn
```
