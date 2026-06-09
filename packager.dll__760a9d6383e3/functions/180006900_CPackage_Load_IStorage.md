# CPackage::Load(IStorage *)

- ea: `0x180006900`
- end: `0x180006adf`
- name: `?Load@CPackage@@UEAAJPEAUIStorage@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(CPackage *this, struct IStorage *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006900`
- `0x180009370`
- `0x180009fa0`
- `0x18000cba6`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `ole32!ReadClassStg` at `0x180006958`
- `ole32!ReadClassStg` at `0x180006958`

## pseudocode

```c
__int64 __fastcall CPackage::Load(CPackage *this, struct IStorage *a2)
{
  bool v2; // zf
  int v5; // ebx
  struct IStream *v7; // [rsp+40h] [rbp-20h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-18h] BYREF

  v2 = *((_DWORD *)this + 17) == 0;
  pclsid = 0;
  v7 = 0;
  if ( !v2 )
    return (unsigned int)-2147418113;
  if ( a2 )
  {
    if ( ReadClassStg(a2, &pclsid) >= 0 )
    {
      if ( !memcmp_0(&pclsid, &CLSID_SOUNDREC, 0x10u)
        || !memcmp_0(&pclsid, &CLSID_OLE1SOUNDREC, 0x10u)
        || !memcmp_0(&pclsid, &CLSID_MPlayer, 0x10u)
        || !memcmp_0(&pclsid, &CLSID_OLE1MPlayer, 0x10u)
        || !memcmp_0(&pclsid, &CLSID_AVIFile, 0x10u)
        || !memcmp_0(&pclsid, &CLSID_MIDFile, 0x10u) )
      {
        return CPackage::LoadMMStorage((CPackage *)((char *)this - 40), a2);
      }
      if ( !memcmp_0(&pclsid, &CLSID_CPackage, 0x10u) || !memcmp_0(&pclsid, &CLSID_OldPackage, 0x10u) )
      {
        v5 = ((__int64 (__fastcall *)(struct IStorage *, __int128 *, _QWORD, __int64, _DWORD, struct IStream **))a2->lpVtbl->OpenStream)(
               a2,
               &xmmword_1800104C8,
               0,
               18,
               0,
               &v7);
        if ( v5 >= 0 )
        {
          v5 = CPackage::PackageReadFromStream((CPackage *)((char *)this - 40), v7);
          if ( v5 >= 0 )
          {
            *((_DWORD *)this + 28) = 0;
            *((_DWORD *)this + 17) = 1;
            *((_DWORD *)this + 22) = 1;
          }
          ((void (__fastcall *)(struct IStream *))v7->lpVtbl->Release)(v7);
        }
        return (unsigned int)v5;
      }
    }
    return (unsigned int)-2147418113;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x180006900  mov     [rsp-18h+arg_10], rbx
0x180006905  mov     [rsp-18h+arg_18], rsi
0x18000690a  push    rbp
0x18000690b  push    rdi
0x18000690c  push    r15
0x18000690e  mov     rbp, rsp
0x180006911  sub     rsp, 60h
0x180006915  mov     rax, cs:__security_cookie
0x18000691c  xor     rax, rsp
0x18000691f  mov     [rbp+var_8], rax
0x180006923  cmp     dword ptr [rcx+44h], 0
0x180006927  xorps   xmm0, xmm0
0x18000692a  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18000692e  mov     rbx, rdx
0x180006931  mov     [rbp+var_20], 0
0x180006939  mov     rdi, rcx
0x18000693c  jnz     loc_180006AB7
0x180006942  test    rdx, rdx
0x180006945  jnz     short loc_180006951
0x180006947  mov     ebx, 80004003h
0x18000694c  jmp     loc_180006ABC
0x180006951  lea     rdx, [rbp+pclsid]; pclsid
0x180006955  mov     rcx, rbx; pStg
0x180006958  call    cs:__imp_ReadClassStg
0x18000695e  test    eax, eax
0x180006960  js      loc_180006AB7
0x180006966  mov     r15d, 10h
0x18000696c  lea     rdx, CLSID_SOUNDREC; Buf2
0x180006973  mov     r8d, r15d; Size
0x180006976  lea     rcx, [rbp+pclsid]; Buf1
0x18000697a  call    memcmp_0
0x18000697f  test    eax, eax
0x180006981  jz      loc_180006AA9
0x180006987  mov     r8d, r15d; Size
0x18000698a  lea     rdx, CLSID_OLE1SOUNDREC; Buf2
0x180006991  lea     rcx, [rbp+pclsid]; Buf1
0x180006995  call    memcmp_0
0x18000699a  test    eax, eax
0x18000699c  jz      loc_180006AA9
0x1800069a2  mov     r8d, r15d; Size
0x1800069a5  lea     rdx, CLSID_MPlayer; Buf2
0x1800069ac  lea     rcx, [rbp+pclsid]; Buf1
0x1800069b0  call    memcmp_0
0x1800069b5  test    eax, eax
0x1800069b7  jz      loc_180006AA9
0x1800069bd  mov     r8d, r15d; Size
0x1800069c0  lea     rdx, CLSID_OLE1MPlayer; Buf2
0x1800069c7  lea     rcx, [rbp+pclsid]; Buf1
0x1800069cb  call    memcmp_0
0x1800069d0  test    eax, eax
0x1800069d2  jz      loc_180006AA9
0x1800069d8  mov     r8d, r15d; Size
0x1800069db  lea     rdx, CLSID_AVIFile; Buf2
0x1800069e2  lea     rcx, [rbp+pclsid]; Buf1
0x1800069e6  call    memcmp_0
0x1800069eb  test    eax, eax
0x1800069ed  jz      loc_180006AA9
0x1800069f3  mov     r8d, r15d; Size
0x1800069f6  lea     rdx, CLSID_MIDFile; Buf2
0x1800069fd  lea     rcx, [rbp+pclsid]; Buf1
0x180006a01  call    memcmp_0
0x180006a06  test    eax, eax
0x180006a08  jz      loc_180006AA9
0x180006a0e  mov     r8d, r15d; Size
0x180006a11  lea     rdx, CLSID_CPackage; Buf2
0x180006a18  lea     rcx, [rbp+pclsid]; Buf1
0x180006a1c  call    memcmp_0
0x180006a21  test    eax, eax
0x180006a23  jz      short loc_180006A3C
0x180006a25  mov     r8d, r15d; Size
0x180006a28  lea     rdx, CLSID_OldPackage; Buf2
0x180006a2f  lea     rcx, [rbp+pclsid]; Buf1
0x180006a33  call    memcmp_0
0x180006a38  test    eax, eax
0x180006a3a  jnz     short loc_180006AB7
0x180006a3c  mov     rax, [rbx]
0x180006a3f  lea     rcx, [rbp+var_20]
0x180006a43  mov     [rsp+60h+var_38], rcx
0x180006a48  lea     rdx, xmmword_1800104C8
0x180006a4f  mov     r9d, 12h
0x180006a55  mov     [rsp+60h+var_40], 0
0x180006a5d  xor     r8d, r8d
0x180006a60  mov     rcx, rbx
0x180006a63  mov     rax, [rax+20h]
0x180006a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6c  mov     ebx, eax
0x180006a6e  test    eax, eax
0x180006a70  js      short loc_180006ABC
0x180006a72  mov     rdx, [rbp+var_20]; struct IStream *
0x180006a76  lea     rcx, [rdi-28h]; this
0x180006a7a  call    ?PackageReadFromStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::PackageReadFromStream(IStream *)
0x180006a7f  mov     ebx, eax
0x180006a81  test    eax, eax
0x180006a83  js      short loc_180006A97
0x180006a85  mov     eax, 1
0x180006a8a  mov     dword ptr [rdi+70h], 0
0x180006a91  mov     [rdi+44h], eax
0x180006a94  mov     [rdi+58h], eax
0x180006a97  mov     rcx, [rbp+var_20]
0x180006a9b  mov     rax, [rcx]
0x180006a9e  mov     rax, [rax+10h]
0x180006aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa7  jmp     short loc_180006ABC
0x180006aa9  mov     rdx, rbx; pStg
0x180006aac  lea     rcx, [rdi-28h]; this
0x180006ab0  call    ?LoadMMStorage@CPackage@@IEAAJPEAUIStorage@@@Z; CPackage::LoadMMStorage(IStorage *)
0x180006ab5  jmp     short loc_180006ABE
0x180006ab7  mov     ebx, 8000FFFFh
0x180006abc  mov     eax, ebx
0x180006abe  mov     rcx, [rbp+var_8]
0x180006ac2  xor     rcx, rsp; StackCookie
0x180006ac5  call    __security_check_cookie
0x180006aca  lea     r11, [rsp+60h+var_s0]
0x180006acf  mov     rbx, [r11+30h]
0x180006ad3  mov     rsi, [r11+38h]
0x180006ad7  mov     rsp, r11
0x180006ada  pop     r15
0x180006adc  pop     rdi
0x180006add  pop     rbp
0x180006ade  retn
```
