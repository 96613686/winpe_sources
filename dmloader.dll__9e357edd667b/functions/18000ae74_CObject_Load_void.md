# CObject::Load(void)

- ea: `0x18000ae74`
- end: `0x18000b352`
- name: `?Load@CObject@@QEAAJXZ`
- size: `1246`
- prototype: `__int64 __fastcall(CObject *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180008bc0`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180009fdc`
- `0x18000a10c`
- `0x18000abec`
- `0x18000ad9c`
- `0x18000ae74`
- `0x18000b358`
- `0x18000c018`
- `0x18000c70c`
- `0x18000cd7c`
- `0x18000d80c`
- `0x18000d8e0`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000af34`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b115`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000af34`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b05a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b115`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aee8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aee8`

## pseudocode

```c
__int64 __fastcall CObject::Load(CObject *this)
{
  union _LARGE_INTEGER *v1; // r15
  HRESULT v4; // ebx
  CFileStream *v5; // rax
  CFileStream *v6; // rbx
  unsigned __int16 *v7; // r8
  unsigned __int16 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  CFileStream *v11; // rsi
  unsigned __int16 *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // r14d
  CFileStream *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  LONGLONG QuadPart; // rcx
  CFileStream *v20; // rax
  __int64 v21; // rcx
  int v22; // esi
  void (*v23)(void); // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v30[176]; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[860]; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned __int16 v33[520]; // [rsp+450h] [rbp+350h] BYREF

  v1 = (union _LARGE_INTEGER *)((char *)this + 8);
  if ( (*((_DWORD *)this + 4) & 0xC10) == 0 )
    return 2289570182LL;
  ppv = 0;
  v4 = CoCreateInstance((const IID *const)((char *)this + 36), 0, 1u, &IID_IDirectMusicObject, &ppv);
  if ( v4 < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  if ( (*((_BYTE *)this + 16) & 0x10) != 0 )
  {
    memset_0(v33, 0, sizeof(v33));
    v5 = (CFileStream *)malloc(0x230u);
    if ( v5 )
    {
      v6 = CFileStream::CFileStream(v5, *(struct CLoader **)(*((_QWORD *)this + 26) + 184LL));
      if ( v6 )
      {
        if ( (*((_BYTE *)this + 16) & 0x20) != 0 )
        {
          v7 = (unsigned __int16 *)*((_QWORD *)this + 11);
          v8 = v33;
          v9 = 260;
          v10 = 520;
          v11 = v6;
          do
          {
            if ( !v9 )
              break;
            if ( !*v7 )
              break;
            *v8++ = *v7++;
            --v9;
            --v10;
          }
          while ( v10 );
          v12 = v8 - 1;
          if ( v10 )
            v12 = v8;
          *v12 = 0;
        }
        else
        {
          CClass::GetPath(*((CClass **)this + 26), v33);
          v14 = -1;
          do
            ++v14;
          while ( v33[v14] );
          StringCchCatNW(v33, v13, *((const unsigned __int16 **)this + 11), 259 - v14);
          v11 = v6;
        }
        v15 = CFileStream::Open(v11, v33, 0x80000000);
        if ( v15 < 0 )
        {
          (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v11 + 16LL))(v11);
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          return (unsigned int)v15;
        }
        goto LABEL_44;
      }
    }
    goto LABEL_41;
  }
  if ( (*((_DWORD *)this + 4) & 0x400) == 0 )
  {
    v6 = 0;
    if ( (*((_DWORD *)this + 4) & 0x800) == 0 )
      goto LABEL_44;
    v20 = (CFileStream *)malloc(0x28u);
    v6 = v20;
    if ( v20 )
    {
      v21 = *(_QWORD *)(*((_QWORD *)this + 26) + 184LL);
      *(_QWORD *)v20 = &CStream::`vftable'{for `IStream'};
      *((_QWORD *)v20 + 1) = &CStream::`vftable'{for `IDirectMusicGetLoader'};
      *((_DWORD *)v20 + 4) = 1;
      *((_QWORD *)v20 + 3) = 0;
      *((_QWORD *)v20 + 4) = v21;
      if ( v21 )
        _InterlockedAdd((volatile signed __int32 *)(v21 + 560), 1u);
      v22 = CStream::Open(v20, *((struct IStream **)this + 14), v1[15]);
      if ( v22 < 0 )
      {
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( ppv )
        {
          v23 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_58:
          v23();
        }
        return (unsigned int)v22;
      }
LABEL_44:
      v29 = 0;
      v22 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStream, &v29);
      if ( v22 >= 0 )
      {
        v24 = *((_QWORD *)this + 23);
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v25 = v29;
        *((_QWORD *)this + 23) = ppv;
        ppv = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, CFileStream *))(*(_QWORD *)v25 + 40LL))(v25, v6);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v22 >= 0 )
        {
          CDescriptor::CDescriptor((CDescriptor *)v30);
          memset_0(v32, 0, 0x354u);
          v27 = *((_QWORD *)this + 23);
          v31 = 856;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 24LL))(v27, &v31);
          CDescriptor::Set((CDescriptor *)v30, (struct _DMUS_OBJECTDESC *)&v31, 0);
          CDescriptor::Merge((CDescriptor *)v1, (struct CDescriptor *)v30);
          *((_DWORD *)this + 4) |= 0x200u;
          CDescriptor::Get((CDescriptor *)v1, (struct _DMUS_OBJECTDESC *)&v31);
          (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 23) + 32LL))(*((_QWORD *)this + 23), &v31);
          CDescriptor::~CDescriptor((CDescriptor *)v30);
        }
        else
        {
          v26 = *((_QWORD *)this + 23);
          if ( v26 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          *((_QWORD *)this + 23) = 0;
        }
        if ( !v6 )
        {
LABEL_56:
          if ( ppv )
          {
            v23 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
            goto LABEL_58;
          }
          return (unsigned int)v22;
        }
      }
      else if ( !v6 )
      {
        goto LABEL_56;
      }
      (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v6 + 16LL))(v6);
      goto LABEL_56;
    }
    goto LABEL_41;
  }
  v16 = (CFileStream *)malloc(0x38u);
  v6 = v16;
  if ( !v16 )
  {
LABEL_41:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 2147942414LL;
  }
  v17 = *(_QWORD *)(*((_QWORD *)this + 26) + 184LL);
  *(_QWORD *)v16 = &CMemStream::`vftable'{for `IStream'};
  *((_QWORD *)v16 + 1) = &CMemStream::`vftable'{for `IDirectMusicGetLoader'};
  *((_DWORD *)v16 + 4) = 1;
  *((_QWORD *)v16 + 3) = 0;
  *((_QWORD *)v16 + 4) = 0;
  *((_QWORD *)v16 + 5) = 0;
  *((_QWORD *)v16 + 6) = v17;
  if ( v17 )
    _InterlockedAdd((volatile signed __int32 *)(v17 + 560), 1u);
  v18 = *((_QWORD *)this + 13);
  QuadPart = v1->QuadPart;
  *((_QWORD *)v6 + 3) = v18;
  *((_QWORD *)v6 + 4) = QuadPart;
  *((_QWORD *)v6 + 5) = 0;
  if ( v18 && QuadPart )
    goto LABEL_44;
  (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 2289570178LL;
}

```

## disassembly

```asm
0x18000ae74  mov     [rsp-8+arg_8], rbx
0x18000ae79  mov     [rsp-8+arg_10], rsi
0x18000ae7e  push    rbp
0x18000ae7f  push    rdi
0x18000ae80  push    r12
0x18000ae82  push    r14
0x18000ae84  push    r15
0x18000ae86  lea     rbp, [rsp-770h]
0x18000ae8e  sub     rsp, 870h
0x18000ae95  mov     rax, cs:__security_cookie
0x18000ae9c  xor     rax, rsp
0x18000ae9f  mov     [rbp+790h+var_30], rax
0x18000aea6  lea     r15, [rcx+8]
0x18000aeaa  mov     rdi, rcx
0x18000aead  test    dword ptr [r15+8], 0C10h
0x18000aeb5  jnz     short loc_18000AEC1
0x18000aeb7  mov     eax, 88781186h
0x18000aebc  jmp     loc_18000B327
0x18000aec1  xor     r12d, r12d
0x18000aec4  lea     rax, [rsp+890h+var_860]
0x18000aec9  add     rcx, 24h ; '$'; rclsid
0x18000aecd  mov     [rsp+890h+var_860], r12
0x18000aed2  lea     r9, IID_IDirectMusicObject; riid
0x18000aed9  mov     [rsp+890h+ppv], rax; ppv
0x18000aede  xor     edx, edx; pUnkOuter
0x18000aee0  lea     r14d, [r12+1]
0x18000aee5  mov     r8d, r14d; dwClsContext
0x18000aee8  call    cs:__imp_CoCreateInstance
0x18000aeee  mov     ebx, eax
0x18000aef0  test    eax, eax
0x18000aef2  jns     short loc_18000AF11
0x18000aef4  mov     rcx, [rsp+890h+var_860]
0x18000aef9  test    rcx, rcx
0x18000aefc  jz      short loc_18000AF0A
0x18000aefe  mov     rdx, [rcx]
0x18000af01  mov     rax, [rdx+10h]
0x18000af05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af0a  mov     eax, ebx
0x18000af0c  jmp     loc_18000B327
0x18000af11  test    byte ptr [rdi+10h], 10h
0x18000af15  jz      loc_18000B048
0x18000af1b  xor     edx, edx; Val
0x18000af1d  lea     rcx, [rbp+790h+var_440]; void *
0x18000af24  mov     r8d, 410h; Size
0x18000af2a  call    memset_0
0x18000af2f  mov     ecx, 230h; Size
0x18000af34  call    cs:__imp_malloc
0x18000af3a  test    rax, rax
0x18000af3d  jz      loc_18000B19E
0x18000af43  mov     rdx, [rdi+0D0h]
0x18000af4a  mov     rcx, rax; this
0x18000af4d  mov     rdx, [rdx+0B8h]; struct CLoader *
0x18000af54  call    ??0CFileStream@@QEAA@PEAVCLoader@@@Z; CFileStream::CFileStream(CLoader *)
0x18000af59  mov     rbx, rax
0x18000af5c  test    rax, rax
0x18000af5f  jz      loc_18000B19E
0x18000af65  test    byte ptr [rdi+10h], 20h
0x18000af69  jz      short loc_18000AFB7
0x18000af6b  mov     r8, [rdi+58h]
0x18000af6f  lea     rax, [rbp+790h+var_440]
0x18000af76  mov     ecx, 104h
0x18000af7b  mov     edx, 208h
0x18000af80  mov     rsi, rbx
0x18000af83  test    rcx, rcx
0x18000af86  jz      short loc_18000AFA6
0x18000af88  movzx   r9d, word ptr [r8]
0x18000af8c  test    r9w, r9w
0x18000af90  jz      short loc_18000AFA6
0x18000af92  mov     [rax], r9w
0x18000af96  add     r8, 2
0x18000af9a  add     rax, 2
0x18000af9e  sub     rcx, r14
0x18000afa1  sub     rdx, r14
0x18000afa4  jnz     short loc_18000AF83
0x18000afa6  test    rdx, rdx
0x18000afa9  lea     rcx, [rax-2]
0x18000afad  cmovnz  rcx, rax
0x18000afb1  mov     [rcx], r12w
0x18000afb5  jmp     short loc_18000AFFB
0x18000afb7  mov     rcx, [rdi+0D0h]; this
0x18000afbe  lea     rdx, [rbp+790h+var_440]; unsigned __int16 *
0x18000afc5  call    ?GetPath@CClass@@QEAAJPEAG@Z; CClass::GetPath(ushort *)
0x18000afca  lea     rcx, [rbp+790h+var_440]
0x18000afd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000afd5  inc     rax
0x18000afd8  cmp     [rcx+rax*2], r12w
0x18000afdd  jnz     short loc_18000AFD5
0x18000afdf  mov     r8, [rdi+58h]; unsigned __int16 *
0x18000afe3  lea     rcx, [rbp+790h+var_440]; unsigned __int16 *
0x18000afea  mov     r9d, 103h
0x18000aff0  sub     r9, rax; unsigned __int64
0x18000aff3  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000aff8  mov     rsi, rbx
0x18000affb  mov     r8d, 80000000h; unsigned int
0x18000b001  lea     rdx, [rbp+790h+var_440]; unsigned __int16 *
0x18000b008  mov     rcx, rsi; this
0x18000b00b  call    ?Open@CFileStream@@QEAAJPEAGK@Z; CFileStream::Open(ushort *,ulong)
0x18000b010  mov     r14d, eax
0x18000b013  test    eax, eax
0x18000b015  jns     loc_18000B1BE
0x18000b01b  mov     rdx, [rsi]
0x18000b01e  mov     rcx, rsi
0x18000b021  mov     rax, [rdx+10h]
0x18000b025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02a  mov     rcx, [rsp+890h+var_860]
0x18000b02f  test    rcx, rcx
0x18000b032  jz      short loc_18000B040
0x18000b034  mov     rdx, [rcx]
0x18000b037  mov     rax, [rdx+10h]
0x18000b03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b040  mov     eax, r14d
0x18000b043  jmp     loc_18000B327
0x18000b048  test    dword ptr [rdi+10h], 400h
0x18000b04f  jz      loc_18000B100
0x18000b055  mov     ecx, 38h ; '8'; Size
0x18000b05a  call    cs:__imp_malloc
0x18000b060  mov     rbx, rax
0x18000b063  test    rax, rax
0x18000b066  jz      loc_18000B19E
0x18000b06c  mov     rax, [rdi+0D0h]
0x18000b073  mov     rcx, [rax+0B8h]
0x18000b07a  lea     rax, ??_7CMemStream@@6BIStream@@@; const CMemStream::`vftable'{for `IStream'}
0x18000b081  mov     [rbx], rax
0x18000b084  lea     rax, ??_7CMemStream@@6BIDirectMusicGetLoader@@@; const CMemStream::`vftable'{for `IDirectMusicGetLoader'}
0x18000b08b  mov     [rbx+8], rax
0x18000b08f  mov     [rbx+10h], r14d
0x18000b093  mov     [rbx+18h], r12
0x18000b097  mov     [rbx+20h], r12
0x18000b09b  mov     [rbx+28h], r12
0x18000b09f  mov     [rbx+30h], rcx
0x18000b0a3  test    rcx, rcx
0x18000b0a6  jz      short loc_18000B0B0
0x18000b0a8  lock add [rcx+230h], r14d
0x18000b0b0  mov     rax, [rdi+68h]
0x18000b0b4  mov     rcx, [r15]
0x18000b0b7  mov     [rbx+18h], rax
0x18000b0bb  mov     [rbx+20h], rcx
0x18000b0bf  mov     [rbx+28h], r12
0x18000b0c3  test    rax, rax
0x18000b0c6  jz      short loc_18000B0D1
0x18000b0c8  test    rcx, rcx
0x18000b0cb  jnz     loc_18000B1BE
0x18000b0d1  mov     rax, [rbx]
0x18000b0d4  mov     rcx, rbx
0x18000b0d7  mov     rax, [rax+10h]
0x18000b0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e0  mov     rcx, [rsp+890h+var_860]
0x18000b0e5  test    rcx, rcx
0x18000b0e8  jz      short loc_18000B0F6
0x18000b0ea  mov     rax, [rcx]
0x18000b0ed  mov     rax, [rax+10h]
0x18000b0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f6  mov     eax, 88781182h
0x18000b0fb  jmp     loc_18000B327
0x18000b100  test    dword ptr [rdi+10h], 800h
0x18000b107  mov     rbx, r12
0x18000b10a  jz      loc_18000B1BE
0x18000b110  mov     ecx, 28h ; '('; Size
0x18000b115  call    cs:__imp_malloc
0x18000b11b  mov     rbx, rax
0x18000b11e  test    rax, rax
0x18000b121  jz      short loc_18000B19E
0x18000b123  mov     rax, [rdi+0D0h]
0x18000b12a  mov     rcx, [rax+0B8h]
0x18000b131  lea     rax, ??_7CStream@@6BIStream@@@; const CStream::`vftable'{for `IStream'}
0x18000b138  mov     [rbx], rax
0x18000b13b  lea     rax, ??_7CStream@@6BIDirectMusicGetLoader@@@; const CStream::`vftable'{for `IDirectMusicGetLoader'}
0x18000b142  mov     [rbx+8], rax
0x18000b146  mov     [rbx+10h], r14d
0x18000b14a  mov     [rbx+18h], r12
0x18000b14e  mov     [rbx+20h], rcx
0x18000b152  test    rcx, rcx
0x18000b155  jz      short loc_18000B15F
0x18000b157  lock add [rcx+230h], r14d
0x18000b15f  mov     r8, [r15+78h]; union _LARGE_INTEGER
0x18000b163  mov     rcx, rbx; this
0x18000b166  mov     rdx, [rdi+70h]; struct IStream *
0x18000b16a  call    ?Open@CStream@@QEAAJPEAUIStream@@T_LARGE_INTEGER@@@Z; CStream::Open(IStream *,_LARGE_INTEGER)
0x18000b16f  mov     esi, eax
0x18000b171  test    eax, eax
0x18000b173  jns     short loc_18000B1BE
0x18000b175  mov     rcx, [rbx]
0x18000b178  mov     rax, [rcx+10h]
0x18000b17c  mov     rcx, rbx
0x18000b17f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b184  mov     rcx, [rsp+890h+var_860]
0x18000b189  test    rcx, rcx
0x18000b18c  jz      loc_18000B325
0x18000b192  mov     rdx, [rcx]
0x18000b195  mov     rax, [rdx+10h]
0x18000b199  jmp     loc_18000B320
0x18000b19e  mov     rcx, [rsp+890h+var_860]
0x18000b1a3  test    rcx, rcx
0x18000b1a6  jz      short loc_18000B1B4
0x18000b1a8  mov     rax, [rcx]
0x18000b1ab  mov     rax, [rax+10h]
0x18000b1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b4  mov     eax, 8007000Eh
0x18000b1b9  jmp     loc_18000B327
0x18000b1be  mov     rcx, [rsp+890h+var_860]
0x18000b1c3  lea     r8, [rsp+890h+var_858]
0x18000b1c8  mov     [rsp+890h+var_858], r12
0x18000b1cd  lea     rdx, IID_IPersistStream
0x18000b1d4  mov     rax, [rcx]
0x18000b1d7  mov     rax, [rax]
0x18000b1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1df  mov     esi, eax
0x18000b1e1  test    eax, eax
0x18000b1e3  jns     short loc_18000B1FA
0x18000b1e5  test    rbx, rbx
0x18000b1e8  jz      loc_18000B30F
0x18000b1ee  mov     rcx, [rbx]
0x18000b1f1  mov     rax, [rcx+10h]
0x18000b1f5  jmp     loc_18000B307
0x18000b1fa  mov     rcx, [rdi+0B8h]
0x18000b201  test    rcx, rcx
0x18000b204  jz      short loc_18000B212
0x18000b206  mov     rax, [rcx]
0x18000b209  mov     rax, [rax+10h]
0x18000b20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b212  mov     rax, [rsp+890h+var_860]
0x18000b217  mov     rdx, rbx
0x18000b21a  mov     rcx, [rsp+890h+var_858]
0x18000b21f  mov     [rdi+0B8h], rax
0x18000b226  mov     [rsp+890h+var_860], r12
0x18000b22b  mov     rax, [rcx]
0x18000b22e  mov     rax, [rax+28h]
0x18000b232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b237  mov     rcx, [rsp+890h+var_858]
0x18000b23c  mov     esi, eax
0x18000b23e  mov     rdx, [rcx]
0x18000b241  mov     rax, [rdx+10h]
0x18000b245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b24a  test    esi, esi
0x18000b24c  jns     short loc_18000B272
0x18000b24e  mov     rcx, [rdi+0B8h]
0x18000b255  test    rcx, rcx
0x18000b258  jz      short loc_18000B266
0x18000b25a  mov     rax, [rcx]
0x18000b25d  mov     rax, [rax+10h]
0x18000b261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b266  mov     [rdi+0B8h], r12
0x18000b26d  jmp     loc_18000B2FB
0x18000b272  lea     rcx, [rsp+890h+var_850]; this
0x18000b277  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000b27c  xor     edx, edx; Val
0x18000b27e  lea     rcx, [rbp+790h+var_79C]; void *
0x18000b282  mov     r8d, 354h; Size
0x18000b288  call    memset_0
0x18000b28d  mov     rcx, [rdi+0B8h]
0x18000b294  lea     rdx, [rbp+790h+var_7A0]
0x18000b298  mov     [rbp+790h+var_7A0], 358h
0x18000b29f  mov     rax, [rcx]
0x18000b2a2  mov     rax, [rax+18h]
0x18000b2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ab  xor     r8d, r8d; struct IStream *
0x18000b2ae  lea     rdx, [rbp+790h+var_7A0]; struct _DMUS_OBJECTDESC *
0x18000b2b2  lea     rcx, [rsp+890h+var_850]; this
0x18000b2b7  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000b2bc  lea     rdx, [rsp+890h+var_850]; struct CDescriptor *
0x18000b2c1  mov     rcx, r15; this
0x18000b2c4  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x18000b2c9  bts     dword ptr [rdi+10h], 9
0x18000b2ce  lea     rdx, [rbp+790h+var_7A0]; struct _DMUS_OBJECTDESC *
0x18000b2d2  mov     rcx, r15; this
0x18000b2d5  call    ?Get@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@@Z; CDescriptor::Get(_DMUS_OBJECTDESC *)
0x18000b2da  mov     rcx, [rdi+0B8h]
0x18000b2e1  lea     rdx, [rbp+790h+var_7A0]
0x18000b2e5  mov     rax, [rcx]
0x18000b2e8  mov     rax, [rax+20h]
0x18000b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2f1  lea     rcx, [rsp+890h+var_850]; this
0x18000b2f6  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000b2fb  test    rbx, rbx
0x18000b2fe  jz      short loc_18000B30F
0x18000b300  mov     rax, [rbx]
0x18000b303  mov     rax, [rax+10h]
0x18000b307  mov     rcx, rbx
0x18000b30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30f  mov     rcx, [rsp+890h+var_860]
0x18000b314  test    rcx, rcx
0x18000b317  jz      short loc_18000B325
0x18000b319  mov     rax, [rcx]
0x18000b31c  mov     rax, [rax+10h]
0x18000b320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b325  mov     eax, esi
0x18000b327  mov     rcx, [rbp+790h+var_30]
0x18000b32e  xor     rcx, rsp; StackCookie
0x18000b331  call    __security_check_cookie
0x18000b336  lea     r11, [rsp+890h+var_20]
0x18000b33e  mov     rbx, [r11+38h]
0x18000b342  mov     rsi, [r11+40h]
0x18000b346  mov     rsp, r11
0x18000b349  pop     r15
0x18000b34b  pop     r14
0x18000b34d  pop     r12
0x18000b34f  pop     rdi
0x18000b350  pop     rbp
0x18000b351  retn
```
