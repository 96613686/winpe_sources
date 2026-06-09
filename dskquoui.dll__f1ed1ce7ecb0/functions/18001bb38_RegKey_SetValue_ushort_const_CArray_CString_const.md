# RegKey::SetValue(ushort const *,CArray<CString> const &)

- ea: `0x18001bb38`
- end: `0x18001bd1a`
- name: `?SetValue@RegKey@@QEAAJPEBGAEBV?$CArray@VCString@@@@@Z`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000fc54`

## callees

- `0x180006ec0`
- `0x180019ee0`
- `0x18001a708`
- `0x18001b8fc`
- `0x18001bb38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd01`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bce0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegKey::SetValue(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // r15d
  unsigned __int64 v6; // rbx
  unsigned int i; // edi
  CString *v8; // rax
  BYTE *lpData; // rdi
  BYTE *v10; // rsi
  unsigned int j; // r14d
  __int64 v12; // rcx
  __int16 *v13; // rdx
  unsigned __int64 v14; // rax
  BYTE *v15; // r8
  __int64 v16; // r9
  __int16 v17; // r10
  __int64 v18; // rdx
  BYTE *v19; // rcx
  int v20; // r14d
  int v21; // r15d
  unsigned int k; // ebx
  CString *v23; // rax
  LSTATUS v24; // eax
  unsigned int v25; // ebx
  char v27[8]; // [rsp+30h] [rbp-78h] BYREF
  __int16 **v28; // [rsp+38h] [rbp-70h]
  void **v29; // [rsp+40h] [rbp-68h]
  BOOL v30; // [rsp+48h] [rbp-60h]
  BYTE *v31; // [rsp+50h] [rbp-58h]

  v5 = *(_DWORD *)(a3 + 12);
  v6 = 1;
  for ( i = 0; (int)i < v5; ++i )
  {
    v8 = (CString *)CArray<CString>::operator[](a3, v27, i);
    v6 += (int)(CString::Length(v8) + 1);
    CString::~CString((CString *)v27);
  }
  lpData = (BYTE *)operator new(saturated_mul(v6, 2u));
  v10 = lpData;
  for ( j = 0; (int)j < v5; ++j )
  {
    CArray<CString>::operator[](a3, v27, j);
    if ( v6 )
    {
      if ( v6 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        v13 = *v28;
        v14 = v6;
        v15 = v10;
        v16 = 0;
        do
        {
          if ( !v12 )
            break;
          v17 = *v13;
          if ( !*v13 )
            break;
          ++v13;
          *(_WORD *)v15 = v17;
          v15 += 2;
          --v12;
          ++v16;
          --v14;
        }
        while ( v14 );
        v18 = v16 - 1;
        if ( v14 )
          v18 = v16;
        v19 = v15 - 2;
        if ( v14 )
          v19 = v15;
        *(_WORD *)v19 = 0;
        v10 += 2 * v18;
        v6 -= v18;
      }
      else
      {
        *(_WORD *)v10 = 0;
      }
    }
    v10 += 2;
    --v6;
    CString::~CString((CString *)v27);
  }
  *(_WORD *)v10 = 0;
  v30 = lpData != 0;
  v31 = lpData;
  v29 = &array_autoptr<char>::`vftable';
  v20 = 1;
  v21 = *(_DWORD *)(a3 + 12);
  for ( k = 0; (int)k < v21; ++k )
  {
    v23 = (CString *)CArray<CString>::operator[](a3, v27, k);
    v20 += CString::Length(v23) + 1;
    CString::~CString((CString *)v27);
  }
  v24 = RegSetValueExW(*(HKEY *)(a1 + 16), L"FindMRU", 0, 7u, lpData, 2 * v20);
  v25 = v24;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  if ( lpData )
    LocalFree(lpData);
  return v25;
}

```

## disassembly

```asm
0x18001bb38  push    rbx
0x18001bb3a  push    rbp
0x18001bb3b  push    rsi
0x18001bb3c  push    rdi
0x18001bb3d  push    r12
0x18001bb3f  push    r13
0x18001bb41  push    r14
0x18001bb43  push    r15
0x18001bb45  sub     rsp, 68h
0x18001bb49  mov     rbp, r8
0x18001bb4c  mov     r13, rcx
0x18001bb4f  mov     r15d, [r8+0Ch]
0x18001bb53  mov     ebx, 1
0x18001bb58  xor     r12d, r12d
0x18001bb5b  mov     edi, r12d
0x18001bb5e  test    r15d, r15d
0x18001bb61  jle     short loc_18001BB93
0x18001bb63  mov     r8d, edi
0x18001bb66  lea     rdx, [rsp+0A8h+var_78]
0x18001bb6b  mov     rcx, rbp
0x18001bb6e  call    ??A?$CArray@VCString@@@@QEBA?AVCString@@H@Z; CArray<CString>::operator[](int)
0x18001bb73  mov     rcx, rax; this
0x18001bb76  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001bb7b  inc     eax
0x18001bb7d  cdqe
0x18001bb7f  add     rbx, rax
0x18001bb82  lea     rcx, [rsp+0A8h+var_78]; this
0x18001bb87  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001bb8c  inc     edi
0x18001bb8e  cmp     edi, r15d
0x18001bb91  jl      short loc_18001BB63
0x18001bb93  mov     eax, 2
0x18001bb98  mul     rbx
0x18001bb9b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bba2  cmovb   rax, rcx
0x18001bba6  mov     rcx, rax; uBytes
0x18001bba9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bbae  mov     rdi, rax
0x18001bbb1  mov     rsi, rax
0x18001bbb4  mov     r14d, r12d
0x18001bbb7  test    r15d, r15d
0x18001bbba  jle     loc_18001BC5C
0x18001bbc0  mov     r8d, r14d
0x18001bbc3  lea     rdx, [rsp+0A8h+var_78]
0x18001bbc8  mov     rcx, rbp
0x18001bbcb  call    ??A?$CArray@VCString@@@@QEBA?AVCString@@H@Z; CArray<CString>::operator[](int)
0x18001bbd0  test    rbx, rbx
0x18001bbd3  jz      short loc_18001BC3F
0x18001bbd5  cmp     rbx, 7FFFFFFFh
0x18001bbdc  jbe     short loc_18001BBE4
0x18001bbde  mov     [rsi], r12w
0x18001bbe2  jmp     short loc_18001BC3F
0x18001bbe4  mov     ecx, 7FFFFFFEh
0x18001bbe9  mov     rax, [rsp+0A8h+var_70]
0x18001bbee  mov     rdx, [rax]
0x18001bbf1  mov     rax, rbx
0x18001bbf4  mov     r8, rsi
0x18001bbf7  mov     r9, r12
0x18001bbfa  test    rcx, rcx
0x18001bbfd  jz      short loc_18001BC21
0x18001bbff  movzx   r10d, word ptr [rdx]
0x18001bc03  test    r10w, r10w
0x18001bc07  jz      short loc_18001BC21
0x18001bc09  add     rdx, 2
0x18001bc0d  mov     [r8], r10w
0x18001bc11  add     r8, 2
0x18001bc15  dec     rcx
0x18001bc18  inc     r9
0x18001bc1b  sub     rax, 1
0x18001bc1f  jnz     short loc_18001BBFA
0x18001bc21  lea     rdx, [r9-1]
0x18001bc25  test    rax, rax
0x18001bc28  cmovnz  rdx, r9
0x18001bc2c  lea     rcx, [r8-2]
0x18001bc30  cmovnz  rcx, r8
0x18001bc34  mov     [rcx], r12w
0x18001bc38  lea     rsi, [rsi+rdx*2]
0x18001bc3c  sub     rbx, rdx
0x18001bc3f  add     rsi, 2
0x18001bc43  dec     rbx
0x18001bc46  lea     rcx, [rsp+0A8h+var_78]; this
0x18001bc4b  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001bc50  inc     r14d
0x18001bc53  cmp     r14d, r15d
0x18001bc56  jl      loc_18001BBC0
0x18001bc5c  mov     [rsi], r12w
0x18001bc60  mov     esi, r12d
0x18001bc63  test    rdi, rdi
0x18001bc66  setnz   sil
0x18001bc6a  mov     [rsp+0A8h+var_60], esi
0x18001bc6e  mov     [rsp+0A8h+var_58], rdi
0x18001bc73  lea     rax, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x18001bc7a  mov     [rsp+0A8h+var_68], rax
0x18001bc7f  mov     r14d, 1
0x18001bc85  mov     r15d, [rbp+0Ch]
0x18001bc89  mov     ebx, r12d
0x18001bc8c  test    r15d, r15d
0x18001bc8f  jle     short loc_18001BCBF
0x18001bc91  mov     r8d, ebx
0x18001bc94  lea     rdx, [rsp+0A8h+var_78]
0x18001bc99  mov     rcx, rbp
0x18001bc9c  call    ??A?$CArray@VCString@@@@QEBA?AVCString@@H@Z; CArray<CString>::operator[](int)
0x18001bca1  mov     rcx, rax; this
0x18001bca4  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001bca9  inc     eax
0x18001bcab  add     r14d, eax
0x18001bcae  lea     rcx, [rsp+0A8h+var_78]; this
0x18001bcb3  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001bcb8  inc     ebx
0x18001bcba  cmp     ebx, r15d
0x18001bcbd  jl      short loc_18001BC91
0x18001bcbf  lea     eax, [r14+r14]
0x18001bcc3  mov     [rsp+0A8h+cbData], eax; cbData
0x18001bcc7  mov     [rsp+0A8h+lpData], rdi; lpData
0x18001bccc  mov     r9d, 7; dwType
0x18001bcd2  xor     r8d, r8d; Reserved
0x18001bcd5  lea     rdx, aFindmru; "FindMRU"
0x18001bcdc  mov     rcx, [r13+10h]; hKey
0x18001bce0  call    cs:__imp_RegSetValueExW
0x18001bce6  mov     ebx, eax
0x18001bce8  test    eax, eax
0x18001bcea  jle     short loc_18001BCF5
0x18001bcec  movzx   ebx, ax
0x18001bcef  or      ebx, 80070000h
0x18001bcf5  test    esi, esi
0x18001bcf7  jz      short loc_18001BD07
0x18001bcf9  test    rdi, rdi
0x18001bcfc  jz      short loc_18001BD07
0x18001bcfe  mov     rcx, rdi; hMem
0x18001bd01  call    cs:__imp_LocalFree
0x18001bd07  mov     eax, ebx
0x18001bd09  add     rsp, 68h
0x18001bd0d  pop     r15
0x18001bd0f  pop     r14
0x18001bd11  pop     r13
0x18001bd13  pop     r12
0x18001bd15  pop     rdi
0x18001bd16  pop     rsi
0x18001bd17  pop     rbp
0x18001bd18  pop     rbx
0x18001bd19  retn
```
