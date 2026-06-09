# CObject::ParseFromFile(void)

- ea: `0x18000b45c`
- end: `0x18000b660`
- name: `?ParseFromFile@CObject@@QEAAJXZ`
- size: `516`
- prototype: `__int64 __fastcall(CObject *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180008e90`
- `0x180009b20`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000ad9c`
- `0x18000b358`
- `0x18000b45c`
- `0x18000c018`
- `0x18000c70c`
- `0x18000cd7c`
- `0x18000d80c`
- `0x18000db40`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4d4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4ab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b4ab`

## pseudocode

```c
__int64 __fastcall CObject::ParseFromFile(CObject *this)
{
  HRESULT v2; // ebx
  CFileStream *v3; // rax
  CFileStream *v4; // rsi
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[176]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v16[860]; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned __int16 v17[520]; // [rsp+450h] [rbp+350h] BYREF

  ppv = 0;
  v2 = CoCreateInstance((const IID *const)((char *)this + 36), 0, 1u, &IID_IDirectMusicObject, &ppv);
  if ( v2 >= 0 )
  {
    memset_0(v17, 0, sizeof(v17));
    v3 = (CFileStream *)malloc(0x230u);
    if ( v3 )
    {
      v4 = CFileStream::CFileStream(v3, *(struct CLoader **)(*((_QWORD *)this + 26) + 184LL));
      v2 = -2147024882;
      if ( v4 )
      {
        if ( (*((_BYTE *)this + 16) & 0x20) != 0 )
        {
          v5 = (unsigned __int16 *)*((_QWORD *)this + 11);
          v6 = v17;
          v7 = 260;
          v8 = 520;
          do
          {
            if ( !v7 )
              break;
            if ( !*v5 )
              break;
            *v6++ = *v5++;
            --v7;
            --v8;
          }
          while ( v8 );
          v9 = v6 - 1;
          if ( v8 )
            v9 = v6;
          *v9 = 0;
        }
        else
        {
          CClass::GetPath(*((CClass **)this + 26), v17);
          v11 = -1;
          do
            ++v11;
          while ( v17[v11] );
          StringCchCatNW(v17, v10, *((const unsigned __int16 **)this + 11), 259 - v11);
        }
        v2 = CFileStream::Open(v4, v17, 0x80000000);
        if ( v2 >= 0 )
        {
          memset_0(v16, 0, 0x354u);
          v15 = 856;
          v2 = (*(__int64 (__fastcall **)(LPVOID, CFileStream *, int *))(*(_QWORD *)ppv + 40LL))(ppv, v4, &v15);
          if ( v2 >= 0 )
          {
            CDescriptor::CDescriptor((CDescriptor *)v14);
            CDescriptor::Set((CDescriptor *)v14, (struct _DMUS_OBJECTDESC *)&v15, 0);
            CDescriptor::Merge((CObject *)((char *)this + 8), (struct CDescriptor *)v14);
            CDescriptor::~CDescriptor((CDescriptor *)v14);
          }
        }
        CFileStream::Release(v4);
      }
    }
    else
    {
      v2 = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b45c  push    rbp
0x18000b45e  push    rbx
0x18000b45f  push    rsi
0x18000b460  push    rdi
0x18000b461  push    r14
0x18000b463  push    r15
0x18000b465  lea     rbp, [rsp-778h]
0x18000b46d  sub     rsp, 878h
0x18000b474  mov     rax, cs:__security_cookie
0x18000b47b  xor     rax, rsp
0x18000b47e  mov     [rbp+7A0h+var_40], rax
0x18000b485  xor     r15d, r15d
0x18000b488  lea     rax, [rsp+8A0h+var_870]
0x18000b48d  mov     rdi, rcx
0x18000b490  mov     [rsp+8A0h+var_870], r15
0x18000b495  add     rcx, 24h ; '$'; rclsid
0x18000b499  mov     [rsp+8A0h+ppv], rax; ppv
0x18000b49e  lea     r9, IID_IDirectMusicObject; riid
0x18000b4a5  xor     edx, edx; pUnkOuter
0x18000b4a7  lea     r8d, [r15+1]; dwClsContext
0x18000b4ab  call    cs:__imp_CoCreateInstance
0x18000b4b1  mov     ebx, eax
0x18000b4b3  test    eax, eax
0x18000b4b5  js      loc_18000B63F
0x18000b4bb  xor     edx, edx; Val
0x18000b4bd  lea     rcx, [rbp+7A0h+var_450]; void *
0x18000b4c4  mov     r8d, 410h; Size
0x18000b4ca  call    memset_0
0x18000b4cf  mov     ecx, 230h; Size
0x18000b4d4  call    cs:__imp_malloc
0x18000b4da  test    rax, rax
0x18000b4dd  jz      loc_18000B629
0x18000b4e3  mov     rdx, [rdi+0D0h]
0x18000b4ea  mov     rcx, rax; this
0x18000b4ed  mov     rdx, [rdx+0B8h]; struct CLoader *
0x18000b4f4  call    ??0CFileStream@@QEAA@PEAVCLoader@@@Z; CFileStream::CFileStream(CLoader *)
0x18000b4f9  mov     rsi, rax
0x18000b4fc  mov     ebx, 8007000Eh
0x18000b501  test    rax, rax
0x18000b504  jz      loc_18000B62E
0x18000b50a  test    byte ptr [rdi+10h], 20h
0x18000b50e  jz      short loc_18000B55A
0x18000b510  mov     r8, [rdi+58h]
0x18000b514  lea     rax, [rbp+7A0h+var_450]
0x18000b51b  mov     ecx, 104h
0x18000b520  mov     edx, 208h
0x18000b525  test    rcx, rcx
0x18000b528  jz      short loc_18000B549
0x18000b52a  movzx   r9d, word ptr [r8]
0x18000b52e  test    r9w, r9w
0x18000b532  jz      short loc_18000B549
0x18000b534  mov     [rax], r9w
0x18000b538  add     r8, 2
0x18000b53c  add     rax, 2
0x18000b540  dec     rcx
0x18000b543  sub     rdx, 1
0x18000b547  jnz     short loc_18000B525
0x18000b549  test    rdx, rdx
0x18000b54c  lea     rcx, [rax-2]
0x18000b550  cmovnz  rcx, rax
0x18000b554  mov     [rcx], r15w
0x18000b558  jmp     short loc_18000B59B
0x18000b55a  mov     rcx, [rdi+0D0h]; this
0x18000b561  lea     rdx, [rbp+7A0h+var_450]; unsigned __int16 *
0x18000b568  call    ?GetPath@CClass@@QEAAJPEAG@Z; CClass::GetPath(ushort *)
0x18000b56d  lea     rcx, [rbp+7A0h+var_450]
0x18000b574  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b578  inc     rax
0x18000b57b  cmp     [rcx+rax*2], r15w
0x18000b580  jnz     short loc_18000B578
0x18000b582  mov     r8, [rdi+58h]; unsigned __int16 *
0x18000b586  lea     rcx, [rbp+7A0h+var_450]; unsigned __int16 *
0x18000b58d  mov     r9d, 103h
0x18000b593  sub     r9, rax; unsigned __int64
0x18000b596  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000b59b  mov     r8d, 80000000h; unsigned int
0x18000b5a1  lea     rdx, [rbp+7A0h+var_450]; unsigned __int16 *
0x18000b5a8  mov     rcx, rsi; this
0x18000b5ab  call    ?Open@CFileStream@@QEAAJPEAGK@Z; CFileStream::Open(ushort *,ulong)
0x18000b5b0  mov     ebx, eax
0x18000b5b2  test    eax, eax
0x18000b5b4  js      short loc_18000B61F
0x18000b5b6  xor     edx, edx; Val
0x18000b5b8  lea     rcx, [rbp+7A0h+var_7AC]; void *
0x18000b5bc  mov     r8d, 354h; Size
0x18000b5c2  call    memset_0
0x18000b5c7  mov     rcx, [rsp+8A0h+var_870]
0x18000b5cc  lea     r8, [rbp+7A0h+var_7B0]
0x18000b5d0  mov     [rbp+7A0h+var_7B0], 358h
0x18000b5d7  mov     rdx, rsi
0x18000b5da  mov     rax, [rcx]
0x18000b5dd  mov     rax, [rax+28h]
0x18000b5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e6  mov     ebx, eax
0x18000b5e8  test    eax, eax
0x18000b5ea  js      short loc_18000B61F
0x18000b5ec  lea     rcx, [rsp+8A0h+var_860]; this
0x18000b5f1  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000b5f6  xor     r8d, r8d; struct IStream *
0x18000b5f9  lea     rdx, [rbp+7A0h+var_7B0]; struct _DMUS_OBJECTDESC *
0x18000b5fd  lea     rcx, [rsp+8A0h+var_860]; this
0x18000b602  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000b607  lea     rdx, [rsp+8A0h+var_860]; struct CDescriptor *
0x18000b60c  lea     rcx, [rdi+8]; this
0x18000b610  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x18000b615  lea     rcx, [rsp+8A0h+var_860]; this
0x18000b61a  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000b61f  mov     rcx, rsi; this
0x18000b622  call    ?Release@CFileStream@@UEAAKXZ; CFileStream::Release(void)
0x18000b627  jmp     short loc_18000B62E
0x18000b629  mov     ebx, 8007000Eh
0x18000b62e  mov     rcx, [rsp+8A0h+var_870]
0x18000b633  mov     rax, [rcx]
0x18000b636  mov     rax, [rax+10h]
0x18000b63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63f  mov     eax, ebx
0x18000b641  mov     rcx, [rbp+7A0h+var_40]
0x18000b648  xor     rcx, rsp; StackCookie
0x18000b64b  call    __security_check_cookie
0x18000b650  add     rsp, 878h
0x18000b657  pop     r15
0x18000b659  pop     r14
0x18000b65b  pop     rdi
0x18000b65c  pop     rsi
0x18000b65d  pop     rbx
0x18000b65e  pop     rbp
0x18000b65f  retn
```
