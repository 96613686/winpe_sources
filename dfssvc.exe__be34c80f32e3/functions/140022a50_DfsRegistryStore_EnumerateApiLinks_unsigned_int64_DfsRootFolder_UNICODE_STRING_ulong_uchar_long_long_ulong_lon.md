# DfsRegistryStore::EnumerateApiLinks(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,ulong,uchar *,long,long *,ulong *,long *,_HEAP_ALLOCATOR *)

- ea: `0x140022a50`
- end: `0x140022edb`
- name: `?EnumerateApiLinks@DfsRegistryStore@@UEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@KPEAEJPEAJPEAK4PEAU_HEAP_ALLOCATOR@@@Z`
- size: `1163`
- prototype: `unsigned int(DfsRegistryStore *__hidden this, unsigned __int64, struct DfsRootFolder *, struct _UNICODE_STRING *, unsigned int, unsigned __int8 *, int, int *, unsigned int *, int *, struct _HEAP_ALLOCATOR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140022a50`
- `0x140037d08`
- `0x140039530`
- `0x140058a70`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140022c5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140022c5c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140022d54`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140022d54`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::EnumerateApiLinks(
        DfsRegistryStore *this,
        HKEY a2,
        struct DfsRootFolder *a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        int a7,
        int *a8,
        unsigned int *a9,
        int *a10,
        struct _HEAP_ALLOCATOR *a11)
{
  signed int v12; // r14d
  unsigned __int8 *v13; // r15
  signed int v14; // r9d
  __int64 result; // rax
  int v16; // r9d
  unsigned int v17; // r10d
  HKEY v18; // r11
  unsigned int v19; // r13d
  bool v20; // si
  DWORD v21; // ecx
  DWORD v22; // edi
  unsigned __int64 v23; // rdx
  unsigned __int8 *v24; // rax
  unsigned int *v25; // r12
  int v26; // r13d
  struct _HEAP_ALLOCATOR *v27; // r14
  struct _HEAP_ALLOCATOR *v28; // rax
  __int64 v29; // rdx
  unsigned int StoreApiInformation; // ebx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rax
  DWORD v33; // eax
  WCHAR *v34; // rax
  WCHAR *v35; // r12
  LSTATUS v36; // eax
  struct _HEAP_ALLOCATOR *v37; // rax
  __int64 v38; // rdx
  DfsStore *v39; // rcx
  DfsStore *v40; // rax
  int v41; // eax
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rax
  int lpcSubKeys; // [rsp+28h] [rbp-81h]
  int lpcSubKeysa; // [rsp+28h] [rbp-81h]
  int v46; // [rsp+68h] [rbp-41h] BYREF
  DWORD dwIndex; // [rsp+6Ch] [rbp-3Dh] BYREF
  int v48; // [rsp+70h] [rbp-39h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-35h] BYREF
  int v50; // [rsp+78h] [rbp-31h]
  DfsStore *v51; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v52; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int8 *v53; // [rsp+90h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+98h] [rbp-11h] BYREF
  signed int v55; // [rsp+9Ch] [rbp-Dh]

  dwIndex = 0;
  v12 = 0;
  v13 = 0;
  v51 = 0;
  v48 = 0;
  v46 = 0;
  v14 = *a8;
  v50 = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v55 = v14;
  result = DfsApiSizeLevelHeader(a5, &dwIndex);
  if ( (_DWORD)result )
    return result;
  v19 = a7;
  v20 = 0;
  v21 = dwIndex * v16;
  v22 = (dwIndex * v16 + 7) & 0xFFFFFFF8;
  if ( (int)(dwIndex * v16) >= a7 )
  {
    v20 = 1;
    v23 = 0;
    v24 = a6;
  }
  else
  {
    v23 = (int)(a7 - v21);
    v24 = &a6[v21];
  }
  v25 = a9;
  v53 = v24;
  v52 = v23;
  if ( a9 )
  {
    v26 = *a9;
    if ( *a9 )
      goto LABEL_19;
    v19 = a7;
  }
  v27 = a11;
  v28 = a11;
  if ( v20 )
    v28 = 0;
  StoreApiInformation = DfsStore::GetStoreApiInformation(
                          this,
                          (__int64)v18,
                          a3,
                          a4,
                          0,
                          v17,
                          0,
                          &v48,
                          &v46,
                          (unsigned __int8 **)&v51,
                          v28);
  if ( v51 )
  {
    v13 = (unsigned __int8 *)v51;
    v48 = v46;
    v50 = v46;
  }
  if ( StoreApiInformation )
    goto LABEL_31;
  v22 += (v46 + 7) & 0xFFFFFFF8;
  if ( !v20 )
  {
    v20 = DfsStore::PackageEnumerationInfo(v51, a5, 0, v13, lpcSubKeys, a6, v19, &v53, &v52) == 111;
    v31 = ((unsigned __int64)(v53 + 7) & 0xFFFFFFFFFFFFFFF8uLL) - (_QWORD)v53;
    if ( v31 <= v52 )
      v32 = v52 - v31;
    else
      v32 = 0;
    v52 = v32;
    v53 = (unsigned __int8 *)((unsigned __int64)(v53 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  v18 = a2;
  v26 = 1;
  v12 = 1;
LABEL_19:
  dwIndex = v26 - 1;
  StoreApiInformation = RegQueryInfoKeyW(v18, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( !StoreApiInformation )
  {
    v33 = cbMaxSubKeyLen;
    if ( cbMaxSubKeyLen >= 0x7FFF )
    {
      StoreApiInformation = 206;
LABEL_24:
      *a10 = v22;
      goto LABEL_25;
    }
    ++cbMaxSubKeyLen;
    v34 = (WCHAR *)operator new(saturated_mul(v33 + 1, 2u));
    if ( !v34 )
    {
      StoreApiInformation = 8;
      goto LABEL_24;
    }
    v35 = v34;
    while ( 1 )
    {
      v48 = v50;
      v46 = 0;
      v51 = 0;
      if ( v55 )
      {
        if ( v12 >= v55 )
          break;
      }
      cchName = cbMaxSubKeyLen;
      v36 = RegEnumKeyExW(a2, dwIndex++, v35, &cchName, 0, 0, 0, 0);
      StoreApiInformation = v36;
      if ( v36 )
        break;
      v37 = a11;
      if ( v20 )
        v37 = 0;
      StoreApiInformation = DfsStore::GetStoreApiInformation(
                              this,
                              (__int64)a2,
                              a3,
                              a4,
                              v35,
                              a5,
                              v13,
                              &v48,
                              &v46,
                              (unsigned __int8 **)&v51,
                              v37);
      v40 = v51;
      if ( v51 )
      {
        if ( v13 )
        {
          (*((void (__fastcall **)(unsigned __int8 *, __int64, _QWORD))a11 + 1))(v13, v38, 0);
          v40 = v51;
        }
        v13 = (unsigned __int8 *)v40;
        v41 = v46;
        v48 = v46;
        v50 = v46;
      }
      else
      {
        v41 = v46;
      }
      if ( StoreApiInformation )
        break;
      v22 += (v41 + 7) & 0xFFFFFFF8;
      if ( !v20 )
      {
        v20 = DfsStore::PackageEnumerationInfo(v39, a5, v12, v13, lpcSubKeysa, a6, a7, &v53, &v52) == 111;
        v42 = ((unsigned __int64)(v53 + 7) & 0xFFFFFFFFFFFFFFF8uLL) - (_QWORD)v53;
        if ( v42 <= v52 )
          v43 = v52 - v42;
        else
          v43 = 0;
        v52 = v43;
        v53 = (unsigned __int8 *)((unsigned __int64)(v53 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
      }
      ++v26;
      ++v12;
    }
    operator delete(v35);
    v25 = a9;
  }
  *a10 = v22;
  if ( StoreApiInformation == 259 )
  {
    if ( !v12 )
      goto LABEL_30;
    if ( !v20 )
    {
      StoreApiInformation = 0;
      goto LABEL_27;
    }
LABEL_57:
    StoreApiInformation = 111;
    goto LABEL_30;
  }
LABEL_25:
  if ( v20 )
    goto LABEL_57;
  if ( !StoreApiInformation )
  {
LABEL_27:
    if ( v25 )
      *v25 = v26;
    *a8 = v12;
  }
LABEL_30:
  v27 = a11;
LABEL_31:
  if ( v13 )
    (*((void (__fastcall **)(unsigned __int8 *, __int64, _QWORD))v27 + 1))(v13, v29, 0);
  return StoreApiInformation;
}

```

## disassembly

```asm
0x140022a50  mov     rax, rsp
0x140022a53  mov     [rax+20h], r9
0x140022a57  mov     [rax+18h], r8
0x140022a5b  mov     [rax+10h], rdx
0x140022a5f  mov     [rax+8], rcx
0x140022a63  push    rbp
0x140022a64  push    rbx
0x140022a65  push    rsi
0x140022a66  push    rdi
0x140022a67  push    r12
0x140022a69  push    r13
0x140022a6b  push    r14
0x140022a6d  push    r15
0x140022a6f  lea     rbp, [rax-47h]
0x140022a73  sub     rsp, 0A8h
0x140022a7a  mov     r10d, [rbp+3Fh+arg_20]
0x140022a7e  xor     ecx, ecx
0x140022a80  mov     rbx, r9
0x140022a83  mov     [rbp+3Fh+dwIndex], ecx
0x140022a86  mov     r9, [rbp+3Fh+arg_38]
0x140022a8d  mov     r14d, ecx
0x140022a90  mov     r15d, ecx
0x140022a93  mov     [rbp+3Fh+var_68], rcx
0x140022a97  mov     [rbp+3Fh+var_78], ecx
0x140022a9a  mov     r11, rdx
0x140022a9d  mov     [rbp+3Fh+var_80], ecx
0x140022aa0  lea     rdx, [rbp+3Fh+dwIndex]
0x140022aa4  mov     r9d, [r9]
0x140022aa7  mov     [rbp+3Fh+var_70], ecx
0x140022aaa  mov     [rbp+3Fh+cbMaxSubKeyLen], ecx
0x140022aad  mov     [rbp+3Fh+cchName], ecx
0x140022ab0  mov     ecx, r10d
0x140022ab3  mov     [rbp+3Fh+var_4C], r9d
0x140022ab7  call    DfsApiSizeLevelHeader
0x140022abc  xor     r8d, r8d
0x140022abf  test    eax, eax
0x140022ac1  jnz     loc_140022CF6
0x140022ac7  mov     r13d, [rbp+3Fh+arg_30]
0x140022acb  lea     eax, [r15+1]
0x140022acf  mov     ecx, r9d
0x140022ad2  mov     sil, r8b
0x140022ad5  imul    ecx, [rbp+3Fh+dwIndex]
0x140022ad9  lea     edi, [rcx+7]
0x140022adc  and     edi, 0FFFFFFF8h
0x140022adf  cmp     ecx, r13d
0x140022ae2  jge     short loc_140022AF5
0x140022ae4  mov     eax, r13d
0x140022ae7  sub     eax, ecx
0x140022ae9  movsxd  rdx, eax
0x140022aec  movsxd  rax, ecx
0x140022aef  add     rax, [rbp+3Fh+arg_28]
0x140022af3  jmp     short loc_140022AFF
0x140022af5  mov     sil, al
0x140022af8  mov     rdx, r8
0x140022afb  mov     rax, [rbp+3Fh+arg_28]
0x140022aff  mov     r12, [rbp+3Fh+arg_40]
0x140022b06  mov     [rbp+3Fh+var_58], rax
0x140022b0a  mov     [rbp+3Fh+var_60], rdx
0x140022b0e  test    r12, r12
0x140022b11  jz      short loc_140022B24
0x140022b13  mov     r13d, [r12]
0x140022b17  test    r13d, r13d
0x140022b1a  jnz     loc_140022C1E
0x140022b20  mov     r13d, [rbp+3Fh+arg_30]
0x140022b24  mov     r14, [rbp+3Fh+arg_50]
0x140022b2b  test    sil, sil
0x140022b2e  mov     rcx, [rbp+3Fh+arg_0]; this
0x140022b32  mov     rax, r14
0x140022b35  cmovnz  rax, r8
0x140022b39  mov     r9, rbx; struct _UNICODE_STRING *
0x140022b3c  mov     [rsp+0E0h+lpcbSecurityDescriptor], rax; struct _HEAP_ALLOCATOR *
0x140022b41  mov     rdx, r11; unsigned __int64
0x140022b44  lea     rax, [rbp+3Fh+var_68]
0x140022b48  mov     [rsp+0E0h+lpcbMaxValueLen], rax; unsigned __int8 **
0x140022b4d  lea     rax, [rbp+3Fh+var_80]
0x140022b51  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; int *
0x140022b56  lea     rax, [rbp+3Fh+var_78]
0x140022b5a  mov     [rsp+0E0h+lpcValues], rax; int *
0x140022b5f  mov     [rsp+0E0h+lpcbMaxClassLen], r8; unsigned __int8 *
0x140022b64  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], r10d; unsigned int
0x140022b69  mov     [rsp+0E0h+lpcSubKeys], r8; int
0x140022b6e  mov     r8, [rbp+3Fh+arg_10]; struct DfsRootFolder *
0x140022b72  call    ?GetStoreApiInformation@DfsStore@@QEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@PEAGKPEAEPEAJ5PEAPEAEPEAU_HEAP_ALLOCATOR@@@Z; DfsStore::GetStoreApiInformation(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,ushort *,ulong,uchar *,long *,long *,uchar * *,_HEAP_ALLOCATOR *)
0x140022b77  mov     rcx, [rbp+3Fh+var_68]; this
0x140022b7b  xor     r8d, r8d; unsigned int
0x140022b7e  mov     ebx, eax
0x140022b80  mov     eax, [rbp+3Fh+var_80]
0x140022b83  test    rcx, rcx
0x140022b86  jz      short loc_140022B91
0x140022b88  mov     r15, rcx
0x140022b8b  mov     [rbp+3Fh+var_78], eax
0x140022b8e  mov     [rbp+3Fh+var_70], eax
0x140022b91  test    ebx, ebx
0x140022b93  jnz     loc_140022CE3
0x140022b99  add     eax, 7
0x140022b9c  and     eax, 0FFFFFFF8h
0x140022b9f  add     edi, eax
0x140022ba1  test    sil, sil
0x140022ba4  jnz     short loc_140022C0F
0x140022ba6  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x140022ba9  lea     rax, [rbp+3Fh+var_60]
0x140022bad  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; unsigned __int64 *
0x140022bb2  mov     r9, r15; unsigned __int8 *
0x140022bb5  lea     rax, [rbp+3Fh+var_58]
0x140022bb9  mov     [rsp+0E0h+lpcValues], rax; unsigned __int8 **
0x140022bbe  mov     rax, [rbp+3Fh+arg_28]
0x140022bc2  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], r13d; unsigned int
0x140022bc7  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x140022bcc  call    ?PackageEnumerationInfo@DfsStore@@IEAAKKKPEAEJ0KPEAPEAEPEA_K@Z; DfsStore::PackageEnumerationInfo(ulong,ulong,uchar *,long,uchar *,ulong,uchar * *,unsigned __int64 *)
0x140022bd1  cmp     eax, 6Fh ; 'o'
0x140022bd4  movzx   esi, sil
0x140022bd8  mov     rax, [rbp+3Fh+var_58]
0x140022bdc  lea     ecx, [rbx+1]
0x140022bdf  cmovz   esi, ecx
0x140022be2  lea     rdx, [rax+7]
0x140022be6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140022bea  mov     rcx, rdx
0x140022bed  sub     rcx, rax
0x140022bf0  mov     rax, [rbp+3Fh+var_60]
0x140022bf4  cmp     rcx, rax
0x140022bf7  jbe     short loc_140022C01
0x140022bf9  xor     r8d, r8d
0x140022bfc  mov     eax, r8d
0x140022bff  jmp     short loc_140022C07
0x140022c01  sub     rax, rcx
0x140022c04  xor     r8d, r8d
0x140022c07  mov     [rbp+3Fh+var_60], rax
0x140022c0b  mov     [rbp+3Fh+var_58], rdx
0x140022c0f  mov     r11, [rbp+3Fh+hKey]
0x140022c13  mov     eax, 1
0x140022c18  mov     r13d, eax
0x140022c1b  mov     r14d, eax
0x140022c1e  mov     [rsp+58h], r8; lpftLastWriteTime
0x140022c23  lea     eax, [r13-1]
0x140022c27  mov     [rsp+0E0h+lpcbSecurityDescriptor], r8; lpcbSecurityDescriptor
0x140022c2c  xor     r9d, r9d; lpReserved
0x140022c2f  mov     [rsp+0E0h+lpcbMaxValueLen], r8; lpcbMaxValueLen
0x140022c34  xor     edx, edx; lpClass
0x140022c36  mov     [rsp+0E0h+lpcbMaxValueNameLen], r8; lpcbMaxValueNameLen
0x140022c3b  mov     rcx, r11; hKey
0x140022c3e  mov     [rsp+0E0h+lpcValues], r8; lpcValues
0x140022c43  mov     [rsp+0E0h+lpcbMaxClassLen], r8; lpcbMaxClassLen
0x140022c48  mov     [rbp+3Fh+dwIndex], eax
0x140022c4b  lea     rax, [rbp+3Fh+cbMaxSubKeyLen]
0x140022c4f  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140022c54  mov     [rsp+0E0h+lpcSubKeys], r8; lpcSubKeys
0x140022c59  xor     r8d, r8d; lpcchClass
0x140022c5c  call    cs:__imp_RegQueryInfoKeyW
0x140022c63  nop     dword ptr [rax+rax+00h]
0x140022c68  xor     r8d, r8d
0x140022c6b  mov     ebx, eax
0x140022c6d  test    eax, eax
0x140022c6f  jnz     loc_140022EA6
0x140022c75  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140022c78  cmp     eax, 7FFFh
0x140022c7d  jb      short loc_140022C86
0x140022c7f  mov     ebx, 0CEh
0x140022c84  jmp     short loc_140022CB3
0x140022c86  inc     eax
0x140022c88  mov     ecx, eax
0x140022c8a  mov     [rbp+3Fh+cbMaxSubKeyLen], eax
0x140022c8d  mov     eax, 2
0x140022c92  mul     rcx
0x140022c95  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140022c9c  cmovo   rax, rcx
0x140022ca0  mov     rcx, rax; Size
0x140022ca3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140022ca8  xor     r8d, r8d
0x140022cab  test    rax, rax
0x140022cae  jnz     short loc_140022D0B
0x140022cb0  lea     ebx, [rax+8]
0x140022cb3  mov     rax, [rbp+3Fh+arg_48]
0x140022cba  mov     [rax], edi
0x140022cbc  test    sil, sil
0x140022cbf  jnz     loc_140022EC9
0x140022cc5  test    ebx, ebx
0x140022cc7  jnz     short loc_140022CDC
0x140022cc9  test    r12, r12
0x140022ccc  jz      short loc_140022CD2
0x140022cce  mov     [r12], r13d
0x140022cd2  mov     rax, [rbp+3Fh+arg_38]
0x140022cd9  mov     [rax], r14d
0x140022cdc  mov     r14, [rbp+3Fh+arg_50]
0x140022ce3  test    r15, r15
0x140022ce6  jz      short loc_140022CF4
0x140022ce8  mov     rax, [r14+8]
0x140022cec  mov     rcx, r15
0x140022cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022cf4  mov     eax, ebx
0x140022cf6  add     rsp, 0A8h
0x140022cfd  pop     r15
0x140022cff  pop     r14
0x140022d01  pop     r13
0x140022d03  pop     r12
0x140022d05  pop     rdi
0x140022d06  pop     rsi
0x140022d07  pop     rbx
0x140022d08  pop     rbp
0x140022d09  retn
0x140022d0b  mov     r12, rax
0x140022d0e  mov     eax, [rbp+3Fh+var_70]
0x140022d11  mov     [rbp+3Fh+var_78], eax
0x140022d14  mov     eax, [rbp+3Fh+var_4C]
0x140022d17  mov     [rbp+3Fh+var_80], r8d
0x140022d1b  mov     [rbp+3Fh+var_68], r8
0x140022d1f  test    eax, eax
0x140022d21  jz      short loc_140022D2C
0x140022d23  cmp     r14d, eax
0x140022d26  jge     loc_140022E94
0x140022d2c  mov     eax, [rbp+3Fh+cbMaxSubKeyLen]
0x140022d2f  lea     r9, [rbp+3Fh+cchName]; lpcchName
0x140022d33  mov     edx, [rbp+3Fh+dwIndex]; dwIndex
0x140022d36  mov     rcx, [rbp+3Fh+hKey]; hKey
0x140022d3a  mov     [rsp+0E0h+lpcValues], r8; lpftLastWriteTime
0x140022d3f  mov     [rsp+0E0h+lpcbMaxClassLen], r8; lpcchClass
0x140022d44  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r8; lpClass
0x140022d49  mov     [rsp+0E0h+lpcSubKeys], r8; lpReserved
0x140022d4e  mov     r8, r12; lpName
0x140022d51  mov     [rbp+3Fh+cchName], eax
0x140022d54  call    cs:__imp_RegEnumKeyExW
0x140022d5b  nop     dword ptr [rax+rax+00h]
0x140022d60  inc     [rbp+3Fh+dwIndex]
0x140022d63  xor     ecx, ecx
0x140022d65  mov     ebx, eax
0x140022d67  test    eax, eax
0x140022d69  jnz     loc_140022E94
0x140022d6f  mov     rax, [rbp+3Fh+arg_50]
0x140022d76  test    sil, sil
0x140022d79  mov     r9, [rbp+3Fh+arg_18]; struct _UNICODE_STRING *
0x140022d7d  mov     r8, [rbp+3Fh+arg_10]; struct DfsRootFolder *
0x140022d81  cmovnz  rax, rcx
0x140022d85  mov     rdx, [rbp+3Fh+hKey]; unsigned __int64
0x140022d89  mov     rcx, [rbp+3Fh+arg_0]; this
0x140022d8d  mov     [rsp+0E0h+lpcbSecurityDescriptor], rax; struct _HEAP_ALLOCATOR *
0x140022d92  lea     rax, [rbp+3Fh+var_68]
0x140022d96  mov     [rsp+0E0h+lpcbMaxValueLen], rax; unsigned __int8 **
0x140022d9b  lea     rax, [rbp+3Fh+var_80]
0x140022d9f  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; int *
0x140022da4  lea     rax, [rbp+3Fh+var_78]
0x140022da8  mov     [rsp+0E0h+lpcValues], rax; int *
0x140022dad  mov     eax, [rbp+3Fh+arg_20]
0x140022db0  mov     [rsp+0E0h+lpcbMaxClassLen], r15; unsigned __int8 *
0x140022db5  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], eax; unsigned int
0x140022db9  mov     [rsp+0E0h+lpcSubKeys], r12; int
0x140022dbe  call    ?GetStoreApiInformation@DfsStore@@QEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@PEAGKPEAEPEAJ5PEAPEAEPEAU_HEAP_ALLOCATOR@@@Z; DfsStore::GetStoreApiInformation(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,ushort *,ulong,uchar *,long *,long *,uchar * *,_HEAP_ALLOCATOR *)
0x140022dc3  mov     ebx, eax
0x140022dc5  xor     r8d, r8d
0x140022dc8  mov     rax, [rbp+3Fh+var_68]
0x140022dcc  test    rax, rax
0x140022dcf  jz      short loc_140022DFE
0x140022dd1  test    r15, r15
0x140022dd4  jz      short loc_140022DF0
0x140022dd6  mov     rax, [rbp+3Fh+arg_50]
0x140022ddd  mov     rcx, r15
0x140022de0  mov     rax, [rax+8]
0x140022de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022de9  mov     rax, [rbp+3Fh+var_68]
0x140022ded  xor     r8d, r8d
0x140022df0  mov     r15, rax
0x140022df3  mov     eax, [rbp+3Fh+var_80]
0x140022df6  mov     [rbp+3Fh+var_78], eax
0x140022df9  mov     [rbp+3Fh+var_70], eax
0x140022dfc  jmp     short loc_140022E01
0x140022dfe  mov     eax, [rbp+3Fh+var_80]
0x140022e01  test    ebx, ebx
0x140022e03  jnz     loc_140022E94
0x140022e09  add     eax, 7
0x140022e0c  and     eax, 0FFFFFFF8h
0x140022e0f  add     edi, eax
0x140022e11  test    sil, sil
0x140022e14  jnz     short loc_140022E84
0x140022e16  mov     edx, [rbp+3Fh+arg_20]; unsigned int
0x140022e19  lea     rax, [rbp+3Fh+var_60]
0x140022e1d  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; unsigned __int64 *
0x140022e22  mov     r9, r15; unsigned __int8 *
0x140022e25  lea     rax, [rbp+3Fh+var_58]
0x140022e29  mov     r8d, r14d; unsigned int
0x140022e2c  mov     [rsp+0E0h+lpcValues], rax; unsigned __int8 **
0x140022e31  mov     eax, [rbp+3Fh+arg_30]
0x140022e34  mov     dword ptr [rsp+0E0h+lpcbMaxClassLen], eax; unsigned int
0x140022e38  mov     rax, [rbp+3Fh+arg_28]
0x140022e3c  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; unsigned __int8 *
0x140022e41  call    ?PackageEnumerationInfo@DfsStore@@IEAAKKKPEAEJ0KPEAPEAEPEA_K@Z; DfsStore::PackageEnumerationInfo(ulong,ulong,uchar *,long,uchar *,ulong,uchar * *,unsigned __int64 *)
0x140022e46  cmp     eax, 6Fh ; 'o'
0x140022e49  movzx   esi, sil
0x140022e4d  lea     eax, [rbx+1]
0x140022e50  cmovz   esi, eax
0x140022e53  mov     rax, [rbp+3Fh+var_58]
0x140022e57  lea     rdx, [rax+7]
0x140022e5b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140022e5f  mov     rcx, rdx
0x140022e62  sub     rcx, rax
0x140022e65  mov     rax, [rbp+3Fh+var_60]
0x140022e69  cmp     rcx, rax
0x140022e6c  jbe     short loc_140022E76
0x140022e6e  xor     r8d, r8d
0x140022e71  mov     eax, r8d
0x140022e74  jmp     short loc_140022E7C
0x140022e76  sub     rax, rcx
0x140022e79  xor     r8d, r8d
  ... truncated ...
```
