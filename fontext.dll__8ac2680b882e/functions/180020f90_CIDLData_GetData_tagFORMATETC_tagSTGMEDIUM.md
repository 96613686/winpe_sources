# CIDLData::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180020f90`
- end: `0x180021172`
- name: `?GetData@CIDLData@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(CIDLData *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011c70`

## callees

- `0x180020f90`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021054`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021054`

## pseudocode

```c
__int64 __fastcall CIDLData::GetData(IUnknown *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r15
  HRESULT StreamOnHGlobal; // ecx
  unsigned int i; // esi
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 result; // rax
  struct IUnknownVtbl *lpVtbl; // r9
  _BYTE v13[16]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v14; // [rsp+40h] [rbp-78h]

  p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a3->hBitmap;
  a3->pUnkForRelease = 0;
  a3->hBitmap = 0;
  StreamOnHGlobal = -2147024809;
  for ( i = 0; i < 0x15; ++i )
  {
    v9 = 4LL * (int)i;
    if ( LOWORD(this[v9 + 5].lpVtbl) == a2->cfFormat
      && ((__int64)this[4 * (int)i + 8].lpVtbl & a2->tymed) != 0
      && LODWORD(this[v9 + 7].lpVtbl) == a2->dwAspect )
    {
      *(_OWORD *)&a3->tymed = *(_OWORD *)&this[3 * (int)i + 89].lpVtbl;
      a3->pUnkForRelease = (IUnknown *)this[3 * (int)i + 91];
      if ( p_hBitmap->hBitmap )
      {
        if ( a3->tymed == 1 )
        {
          ((void (__fastcall *)(IUnknown *))this->lpVtbl->AddRef)(this);
          result = 0;
          a3->pUnkForRelease = this;
          return result;
        }
        if ( a3->tymed == 4 )
        {
          StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)p_hBitmap);
          if ( StreamOnHGlobal >= 0 )
          {
            memset_0(v13, 0, 0x50u);
            if ( (*((int (__fastcall **)(struct IUnknownVtbl *, _BYTE *, __int64))this[3 * (int)i + 90].lpVtbl->QueryInterface
                  + 12))(
                   this[3 * (int)i + 90].lpVtbl,
                   v13,
                   1) >= 0 )
            {
              (*((void (__fastcall **)(struct IUnknownVtbl *, const union _LARGE_INTEGER, _QWORD, _QWORD))this[3 * (int)i + 90].lpVtbl->QueryInterface
               + 5))(
                this[3 * (int)i + 90].lpVtbl,
                CIDLData::m_LargeIntZero,
                0,
                0);
              v10 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, HBITMAP, __int64, _QWORD, _QWORD))this[3 * (int)i + 90].lpVtbl->QueryInterface
                     + 7))(
                      this[3 * (int)i + 90].lpVtbl,
                      p_hBitmap->hBitmap,
                      v14,
                      0,
                      0);
              (*(void (__fastcall **)(HBITMAP, const union _LARGE_INTEGER, _QWORD, _QWORD))(*(_QWORD *)p_hBitmap->hBitmap
                                                                                          + 40LL))(
                p_hBitmap->hBitmap,
                CIDLData::m_LargeIntZero,
                0,
                0);
              return v10;
            }
            StreamOnHGlobal = -2147024882;
          }
        }
      }
    }
  }
  if ( StreamOnHGlobal == -2147024809 )
  {
    lpVtbl = this[4].lpVtbl;
    if ( lpVtbl )
      return (unsigned int)(*((__int64 (__fastcall **)(struct IUnknownVtbl *, struct tagFORMATETC *, struct tagSTGMEDIUM *))lpVtbl->QueryInterface
                            + 3))(
                             this[4].lpVtbl,
                             a2,
                             a3);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x180020f90  mov     [rsp+arg_18], rbx
0x180020f95  push    rbp
0x180020f96  push    rsi
0x180020f97  push    rdi
0x180020f98  push    r14
0x180020f9a  push    r15
0x180020f9c  sub     rsp, 90h
0x180020fa3  mov     rax, cs:__security_cookie
0x180020faa  xor     rax, rsp
0x180020fad  mov     [rsp+0B8h+var_38], rax
0x180020fb5  lea     r15, [r8+8]
0x180020fb9  mov     qword ptr [r8+10h], 0
0x180020fc1  mov     rbx, rcx
0x180020fc4  mov     qword ptr [r15], 0
0x180020fcb  mov     rdi, r8
0x180020fce  mov     r14, rdx
0x180020fd1  mov     ecx, 80070057h
0x180020fd6  xor     esi, esi
0x180020fd8  cmp     esi, 15h
0x180020fdb  jnb     loc_180021121
0x180020fe1  movzx   eax, word ptr [r14]
0x180020fe5  movsxd  r8, esi
0x180020fe8  mov     rdx, r8
0x180020feb  shl     rdx, 5
0x180020fef  cmp     [rdx+rbx+28h], ax
0x180020ff4  jnz     loc_180021098
0x180020ffa  lea     rax, [r8+2]
0x180020ffe  shl     rax, 5
0x180021002  mov     eax, [rax+rbx]
0x180021005  test    [r14+18h], eax
0x180021009  jz      loc_180021098
0x18002100f  mov     eax, [r14+10h]
0x180021013  cmp     [rdx+rbx+38h], eax
0x180021017  jnz     short loc_180021098
0x180021019  lea     rbp, [r8+r8*2]
0x18002101d  movups  xmm0, xmmword ptr [rbx+rbp*8+2C8h]
0x180021025  movups  xmmword ptr [rdi], xmm0
0x180021028  movsd   xmm1, qword ptr [rbx+rbp*8+2D8h]
0x180021031  movsd   qword ptr [rdi+10h], xmm1
0x180021036  cmp     qword ptr [r15], 0
0x18002103a  jz      short loc_180021098
0x18002103c  cmp     dword ptr [rdi], 1
0x18002103f  jz      loc_18002110A
0x180021045  cmp     dword ptr [rdi], 4
0x180021048  jnz     short loc_180021098
0x18002104a  mov     r8, r15; ppstm
0x18002104d  mov     edx, 1; fDeleteOnRelease
0x180021052  xor     ecx, ecx; hGlobal
0x180021054  call    cs:__imp_CreateStreamOnHGlobal
0x18002105a  mov     ecx, eax
0x18002105c  test    eax, eax
0x18002105e  js      short loc_180021098
0x180021060  xor     edx, edx; Val
0x180021062  lea     rcx, [rsp+0B8h+var_88]; void *
0x180021067  lea     r8d, [rdx+50h]; Size
0x18002106b  call    memset_0
0x180021070  mov     rcx, [rbx+rbp*8+2D0h]
0x180021078  lea     rdx, [rsp+0B8h+var_88]
0x18002107d  mov     r8d, 1
0x180021083  mov     rax, [rcx]
0x180021086  mov     rax, [rax+60h]
0x18002108a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002108f  test    eax, eax
0x180021091  jns     short loc_18002109F
0x180021093  mov     ecx, 8007000Eh
0x180021098  inc     esi
0x18002109a  jmp     loc_180020FD8
0x18002109f  mov     rcx, [rbx+rbp*8+2D0h]
0x1800210a7  xor     r9d, r9d
0x1800210aa  mov     rdx, cs:?m_LargeIntZero@CIDLData@@1T_LARGE_INTEGER@@B; _LARGE_INTEGER const CIDLData::m_LargeIntZero
0x1800210b1  xor     r8d, r8d
0x1800210b4  mov     rax, [rcx]
0x1800210b7  mov     rax, [rax+28h]
0x1800210bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210c0  mov     rcx, [rbx+rbp*8+2D0h]
0x1800210c8  xor     r9d, r9d
0x1800210cb  mov     r8, [rsp+0B8h+var_78]
0x1800210d0  mov     rdx, [r15]
0x1800210d3  mov     [rsp+0B8h+var_98], 0
0x1800210dc  mov     rax, [rcx]
0x1800210df  mov     rax, [rax+38h]
0x1800210e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210e8  mov     rcx, [r15]
0x1800210eb  mov     ebx, eax
0x1800210ed  xor     r9d, r9d
0x1800210f0  xor     r8d, r8d
0x1800210f3  mov     rdx, [rcx]
0x1800210f6  mov     rax, [rdx+28h]
0x1800210fa  mov     rdx, cs:?m_LargeIntZero@CIDLData@@1T_LARGE_INTEGER@@B; _LARGE_INTEGER const CIDLData::m_LargeIntZero
0x180021101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021106  mov     eax, ebx
0x180021108  jmp     short loc_18002114B
0x18002110a  mov     rax, [rbx]
0x18002110d  mov     rcx, rbx
0x180021110  mov     rax, [rax+8]
0x180021114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021119  xor     eax, eax
0x18002111b  mov     [rdi+10h], rbx
0x18002111f  jmp     short loc_18002114B
0x180021121  cmp     ecx, 80070057h
0x180021127  jnz     short loc_180021149
0x180021129  mov     r9, [rbx+20h]
0x18002112d  test    r9, r9
0x180021130  jz      short loc_180021149
0x180021132  mov     rax, [r9]
0x180021135  mov     r8, rdi
0x180021138  mov     rdx, r14
0x18002113b  mov     rcx, r9
0x18002113e  mov     rax, [rax+18h]
0x180021142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021147  mov     ecx, eax
0x180021149  mov     eax, ecx
0x18002114b  mov     rcx, [rsp+0B8h+var_38]
0x180021153  xor     rcx, rsp; StackCookie
0x180021156  call    __security_check_cookie
0x18002115b  mov     rbx, [rsp+0B8h+arg_18]
0x180021163  add     rsp, 90h
0x18002116a  pop     r15
0x18002116c  pop     r14
0x18002116e  pop     rdi
0x18002116f  pop     rsi
0x180021170  pop     rbp
0x180021171  retn
```
