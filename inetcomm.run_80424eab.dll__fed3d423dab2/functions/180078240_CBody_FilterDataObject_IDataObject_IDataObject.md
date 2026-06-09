# CBody::FilterDataObject(IDataObject *,IDataObject * *)

- ea: `0x180078240`
- end: `0x1800785a1`
- name: `?FilterDataObject@CBody@@UEAAJPEAUIDataObject@@PEAPEAU2@@Z`
- size: `865`
- prototype: `__int64 __fastcall(CBody *__hidden this, struct IDataObject *, struct IDataObject **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002098`
- `0x180019e28`
- `0x180023b48`
- `0x180078240`
- `0x1800c9fe8`
- `0x1800cc9a2`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!CreateDataObject` at `0x1800784fc`
- `MSOERT2!CreateDataObject` at `0x1800784fc`
- `KERNEL32!GlobalUnlock` at `0x1800783f3`
- `KERNEL32!GlobalUnlock` at `0x1800783f3`
- `KERNEL32!GlobalLock` at `0x180078372`
- `KERNEL32!GlobalLock` at `0x180078372`
- `ole32!ReleaseStgMedium` at `0x18007841b`
- `ole32!ReleaseStgMedium` at `0x18007841b`

## pseudocode

```c
__int64 __fastcall CBody::FilterDataObject(CBody *this, struct IDataObject *a2, struct IDataObject **a3)
{
  struct IDataObject *v4; // r14
  __int64 v5; // rcx
  __int64 result; // rax
  _WORD *v8; // rdi
  unsigned int v9; // esi
  signed int i; // r15d
  struct IDataObjectVtbl *lpVtbl; // rax
  int v12; // ebx
  _BYTE *v13; // r12
  __int64 v14; // rax
  unsigned int v15; // r14d
  __int64 v16; // rax
  int v17; // r8d
  signed int j; // edx
  __int64 v19; // r10
  __int64 v20; // rcx
  unsigned int k; // ecx
  __int64 v22; // rax
  struct IDataObject *v23; // rax
  signed int m; // esi
  size_t Size; // [rsp+20h] [rbp-49h] BYREF
  __int64 v26; // [rsp+28h] [rbp-41h]
  __int128 v27; // [rsp+30h] [rbp-39h] BYREF
  STGMEDIUM hMem; // [rsp+40h] [rbp-29h] BYREF
  __int128 v29; // [rsp+58h] [rbp-11h] BYREF
  __int128 v30; // [rsp+68h] [rbp-1h]
  int v31; // [rsp+D0h] [rbp+67h]
  struct IDataObject *v32; // [rsp+D8h] [rbp+6Fh]
  struct IDataObject **v33; // [rsp+E0h] [rbp+77h]
  struct IDataObject *v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v33 = a3;
  v32 = a2;
  v31 = 851969;
  v34 = 0;
  v26 = 0;
  v4 = a2;
  v5 = *((_QWORD *)this + 20);
  memset(&hMem, 0, sizeof(hMem));
  v29 = 0;
  v30 = 0;
  v27 = 0;
  if ( !v5
    || (result = (*(__int64 (__fastcall **)(__int64, struct IDataObject *))(*(_QWORD *)v5 + 136LL))(v5, a2),
        (_DWORD)result == -2146691327) )
  {
    if ( (*((_BYTE *)this + 96) & 0x20) != 0 && (*((_BYTE *)this + 96) & 4) != 0 && v4 && a3 )
    {
      *a3 = 0;
      v8 = 0;
      v9 = 0;
      for ( i = 0; (unsigned int)i < 2; ++i )
      {
        *(_QWORD *)&v30 = 1;
        DWORD2(v30) = 1;
        LOWORD(v29) = *((_WORD *)&v31 + i);
        if ( ((int (__fastcall *)(struct IDataObject *, __int128 *))v4->lpVtbl->QueryGetData)(v4, &v29) >= 0 )
        {
          lpVtbl = v4->lpVtbl;
          memset(&hMem, 0, sizeof(hMem));
          v12 = ((__int64 (__fastcall *)(struct IDataObject *, __int128 *, STGMEDIUM *))lpVtbl->GetData)(
                  v4,
                  &v29,
                  &hMem);
          if ( v12 >= 0 )
          {
            v13 = GlobalLock(hMem.hBitmap);
            if ( v13 )
            {
              if ( (_WORD)v29 == 1 )
              {
                v14 = -1;
                do
                  ++v14;
                while ( v13[v14] );
                v15 = v14 + 1;
              }
              else
              {
                v16 = -1;
                do
                  ++v16;
                while ( *(_WORD *)&v13[2 * v16] );
                v15 = 2 * v16 + 2;
              }
              *((_DWORD *)&v26 + i) = v15;
              if ( (unsigned int)MemAlloc((void **)&v27 + i, v15) )
              {
                memcpy_0(*((void **)&v27 + i), v13, v15);
                GlobalUnlock(hMem.hBitmap);
                ++v9;
              }
              else
              {
                v12 = -2147024882;
              }
              v4 = v32;
            }
            else
            {
              v12 = -2147467259;
            }
          }
          if ( hMem.pUnkForRelease )
            ((void (__fastcall *)(IUnknown *))hMem.pUnkForRelease->lpVtbl->AddRef)(hMem.pUnkForRelease);
          ReleaseStgMedium(&hMem);
          if ( v12 < 0 )
            goto LABEL_45;
        }
      }
      if ( v9 && (unsigned __int64)(int)v9 <= 2 )
      {
        Size = 0;
        v12 = ULongLongMult(0x30u, (int)v9, &Size);
        if ( v12 >= 0 )
        {
          v8 = ZeroAllocate((unsigned int)Size);
          if ( v8 )
          {
            v17 = 0;
            for ( j = 0; (unsigned int)j < 2; ++j )
            {
              if ( v17 >= (int)v9 )
              {
                v12 = -2147418113;
                goto LABEL_45;
              }
              v19 = *((_QWORD *)&v27 + j);
              if ( v19 )
              {
                v20 = 6LL * v17++;
                v8[4 * v20] = *((_WORD *)&v31 + j);
                *(_DWORD *)&v8[4 * v20 + 20] = *((_DWORD *)&v26 + j);
                *(_DWORD *)&v8[4 * v20 + 8] = 1;
                *(_QWORD *)&v8[4 * v20 + 4] = 0;
                *(_DWORD *)&v8[4 * v20 + 12] = 1;
                *(_DWORD *)&v8[4 * v20 + 10] = -1;
                *(_QWORD *)&v8[4 * v20 + 16] = v19;
              }
            }
            v12 = CreateDataObject(v8, v9, FreeDataObj, &v34);
            if ( v12 >= 0 )
            {
              for ( k = 0; k < 2; ++k )
              {
                v22 = (int)k;
                *((_QWORD *)&v27 + v22) = 0;
              }
              v23 = v34;
              v8 = 0;
              v34 = 0;
              *v33 = v23;
            }
          }
          else
          {
            v12 = -2147024882;
          }
        }
      }
      else
      {
        v12 = -2147467259;
      }
LABEL_45:
      for ( m = 0; (unsigned int)m < 2; ++m )
      {
        if ( *((_QWORD *)&v27 + m) )
        {
          ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
          *((_QWORD *)&v27 + m) = 0;
        }
      }
      if ( v8 )
        ((void (__fastcall *)(LPMALLOC, _WORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v34);
      return (unsigned int)v12;
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180078240  mov     [rsp-8+arg_10], r8
0x180078245  mov     [rsp-8+arg_8], rdx
0x18007824a  push    rbp
0x18007824b  push    rbx
0x18007824c  push    rsi
0x18007824d  push    rdi
0x18007824e  push    r12
0x180078250  push    r13
0x180078252  push    r14
0x180078254  push    r15
0x180078256  lea     rbp, [rsp-1Fh]
0x18007825b  sub     rsp, 88h
0x180078262  xor     eax, eax
0x180078264  mov     [rbp+57h+arg_0], 0D0001h
0x18007826b  xor     r13d, r13d
0x18007826e  mov     [rbp+57h+var_70], rax
0x180078272  xorps   xmm0, xmm0
0x180078275  mov     [rbp+57h+arg_18], r13
0x180078279  xorps   xmm1, xmm1
0x18007827c  mov     [rbp+57h+var_98], r13
0x180078280  mov     rbx, rcx
0x180078283  mov     r14, rdx
0x180078286  mov     rcx, [rcx+0A0h]
0x18007828d  lea     edx, [rax+1]
0x180078290  mov     r12, r8
0x180078293  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180078297  movups  [rbp+57h+var_68], xmm1
0x18007829b  movups  [rbp+57h+var_58], xmm1
0x18007829f  movups  [rbp+57h+var_90], xmm0
0x1800782a3  test    rcx, rcx
0x1800782a6  jz      short loc_1800782C9
0x1800782a8  mov     rax, [rcx]
0x1800782ab  mov     rdx, r14
0x1800782ae  mov     rax, [rax+88h]
0x1800782b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782ba  cmp     eax, 800C1701h
0x1800782bf  jnz     loc_18007858D
0x1800782c5  lea     edx, [r13+1]
0x1800782c9  test    byte ptr [rbx+60h], 20h
0x1800782cd  jz      loc_18007858B
0x1800782d3  test    byte ptr [rbx+60h], 4
0x1800782d7  jz      loc_18007858B
0x1800782dd  test    r14, r14
0x1800782e0  jz      loc_18007858B
0x1800782e6  test    r12, r12
0x1800782e9  jz      loc_18007858B
0x1800782ef  mov     [r12], r13
0x1800782f3  mov     rdi, r13
0x1800782f6  mov     r12d, 1
0x1800782fc  mov     esi, r13d
0x1800782ff  mov     r15d, r13d
0x180078302  cmp     r15d, 2
0x180078306  jnb     loc_18007843C
0x18007830c  movsxd  r13, r15d
0x18007830f  lea     rdx, [rbp+57h+var_68]
0x180078313  mov     rcx, r14
0x180078316  mov     qword ptr [rbp+57h+var_58], 1
0x18007831e  mov     dword ptr [rbp+57h+var_58+8], r12d
0x180078322  movzx   eax, word ptr [rbp+r13*2+57h+arg_0]
0x180078328  mov     word ptr [rbp+57h+var_68], ax
0x18007832c  mov     rax, [r14]
0x18007832f  mov     rax, [rax+28h]
0x180078333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078338  test    eax, eax
0x18007833a  js      loc_18007842B
0x180078340  xor     eax, eax
0x180078342  lea     r8, [rbp+57h+hMem]
0x180078346  mov     [rbp+57h+var_70], rax
0x18007834a  lea     rdx, [rbp+57h+var_68]
0x18007834e  mov     rax, [r14]
0x180078351  xorps   xmm0, xmm0
0x180078354  mov     rcx, r14
0x180078357  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x18007835b  mov     rax, [rax+18h]
0x18007835f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078364  mov     ebx, eax
0x180078366  test    eax, eax
0x180078368  js      loc_1800783FF
0x18007836e  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180078372  call    cs:__imp_GlobalLock
0x180078378  xor     ecx, ecx
0x18007837a  mov     r12, rax
0x18007837d  test    rax, rax
0x180078380  jnz     short loc_180078389
0x180078382  mov     ebx, 80004005h
0x180078387  jmp     short loc_1800783FF
0x180078389  mov     eax, 1
0x18007838e  cmp     word ptr [rbp+57h+var_68], ax
0x180078392  jnz     short loc_1800783A7
0x180078394  or      rax, 0FFFFFFFFFFFFFFFFh
0x180078398  inc     rax
0x18007839b  cmp     [r12+rax], cl
0x18007839f  jnz     short loc_180078398
0x1800783a1  lea     r14d, [rax+1]
0x1800783a5  jmp     short loc_1800783BD
0x1800783a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800783ab  inc     rax
0x1800783ae  cmp     [r12+rax*2], cx
0x1800783b3  jnz     short loc_1800783AB
0x1800783b5  lea     r14d, ds:2[rax*2]
0x1800783bd  lea     rax, [rbp+57h+var_90]
0x1800783c1  mov     dword ptr [rbp+r13*4+57h+var_98], r14d
0x1800783c6  lea     r13, [rax+r13*8]
0x1800783ca  mov     edx, r14d; unsigned int
0x1800783cd  mov     rcx, r13; void **
0x1800783d0  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x1800783d5  test    eax, eax
0x1800783d7  jnz     short loc_1800783E0
0x1800783d9  mov     ebx, 8007000Eh
0x1800783de  jmp     short loc_1800783FB
0x1800783e0  mov     rcx, [r13+0]; void *
0x1800783e4  mov     rdx, r12; Src
0x1800783e7  mov     r8d, r14d; Size
0x1800783ea  call    memcpy_0
0x1800783ef  mov     rcx, [rbp+57h+hMem+8]; hMem
0x1800783f3  call    cs:__imp_GlobalUnlock
0x1800783f9  inc     esi
0x1800783fb  mov     r14, [rbp+57h+arg_8]
0x1800783ff  mov     rcx, [rbp+57h+var_70]
0x180078403  xor     r13d, r13d
0x180078406  test    rcx, rcx
0x180078409  jz      short loc_180078417
0x18007840b  mov     rax, [rcx]
0x18007840e  mov     rax, [rax+8]
0x180078412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078417  lea     rcx, [rbp+57h+hMem]; LPSTGMEDIUM
0x18007841b  call    cs:__imp_ReleaseStgMedium
0x180078421  test    ebx, ebx
0x180078423  js      loc_180078534
0x180078429  jmp     short loc_18007842E
0x18007842b  xor     r13d, r13d
0x18007842e  mov     r12d, 1
0x180078434  add     r15d, r12d
0x180078437  jmp     loc_180078302
0x18007843c  test    esi, esi
0x18007843e  jz      loc_18007852F
0x180078444  movsxd  rdx, esi; unsigned __int64
0x180078447  cmp     rdx, 2
0x18007844b  ja      loc_18007852F
0x180078451  lea     r8, [rbp+57h+Size]; unsigned __int64 *
0x180078455  mov     [rbp+57h+Size], r13
0x180078459  mov     ecx, 30h ; '0'; unsigned __int64
0x18007845e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180078463  mov     ebx, eax
0x180078465  test    eax, eax
0x180078467  js      loc_180078534
0x18007846d  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x180078470  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x180078475  mov     rdi, rax
0x180078478  test    rax, rax
0x18007847b  jnz     short loc_180078487
0x18007847d  mov     ebx, 8007000Eh
0x180078482  jmp     loc_180078534
0x180078487  mov     r8d, r13d
0x18007848a  mov     edx, r13d
0x18007848d  cmp     edx, 2
0x180078490  jnb     short loc_1800784EC
0x180078492  cmp     r8d, esi
0x180078495  jge     short loc_1800784E5
0x180078497  movsxd  r9, edx
0x18007849a  mov     r10, qword ptr [rbp+r9*8+57h+var_90]
0x18007849f  test    r10, r10
0x1800784a2  jz      short loc_1800784E0
0x1800784a4  movsxd  rax, r8d
0x1800784a7  lea     rcx, [rax+rax*2]
0x1800784ab  movzx   eax, word ptr [rbp+r9*2+57h+arg_0]
0x1800784b1  add     rcx, rcx
0x1800784b4  add     r8d, r12d
0x1800784b7  mov     [rdi+rcx*8], ax
0x1800784bb  mov     eax, dword ptr [rbp+r9*4+57h+var_98]
0x1800784c0  mov     [rdi+rcx*8+28h], eax
0x1800784c4  mov     [rdi+rcx*8+10h], r12d
0x1800784c9  mov     [rdi+rcx*8+8], r13
0x1800784ce  mov     [rdi+rcx*8+18h], r12d
0x1800784d3  mov     dword ptr [rdi+rcx*8+14h], 0FFFFFFFFh
0x1800784db  mov     [rdi+rcx*8+20h], r10
0x1800784e0  add     edx, r12d
0x1800784e3  jmp     short loc_18007848D
0x1800784e5  mov     ebx, 8000FFFFh
0x1800784ea  jmp     short loc_180078534
0x1800784ec  lea     r9, [rbp+57h+arg_18]
0x1800784f0  mov     edx, esi
0x1800784f2  lea     r8, ?FreeDataObj@@YAJPEAUtagDATAOBJINFO@@K@Z; FreeDataObj(tagDATAOBJINFO *,ulong)
0x1800784f9  mov     rcx, rdi
0x1800784fc  call    cs:__imp_CreateDataObject
0x180078502  mov     ebx, eax
0x180078504  test    eax, eax
0x180078506  js      short loc_180078534
0x180078508  mov     ecx, r13d
0x18007850b  movsxd  rax, ecx
0x18007850e  add     ecx, r12d
0x180078511  mov     qword ptr [rbp+rax*8+57h+var_90], r13
0x180078516  cmp     ecx, 2
0x180078519  jb      short loc_18007850B
0x18007851b  mov     rax, [rbp+57h+arg_18]
0x18007851f  mov     rdi, r13
0x180078522  mov     rcx, [rbp+57h+arg_10]
0x180078526  mov     [rbp+57h+arg_18], r13
0x18007852a  mov     [rcx], rax
0x18007852d  jmp     short loc_180078534
0x18007852f  mov     ebx, 80004005h
0x180078534  mov     esi, r13d
0x180078537  movsxd  r14, esi
0x18007853a  mov     rdx, qword ptr [rbp+r14*8+57h+var_90]
0x18007853f  test    rdx, rdx
0x180078542  jz      short loc_18007855C
0x180078544  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007854b  mov     rax, [rcx]
0x18007854e  mov     rax, [rax+28h]
0x180078552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078557  mov     qword ptr [rbp+r14*8+57h+var_90], r13
0x18007855c  inc     esi
0x18007855e  cmp     esi, 2
0x180078561  jb      short loc_180078537
0x180078563  test    rdi, rdi
0x180078566  jz      short loc_18007857E
0x180078568  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007856f  mov     rdx, rdi
0x180078572  mov     rax, [rcx]
0x180078575  mov     rax, [rax+28h]
0x180078579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007857e  lea     rcx, [rbp+57h+arg_18]
0x180078582  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180078587  mov     eax, ebx
0x180078589  jmp     short loc_18007858D
0x18007858b  mov     eax, edx
0x18007858d  add     rsp, 88h
0x180078594  pop     r15
0x180078596  pop     r14
0x180078598  pop     r13
0x18007859a  pop     r12
0x18007859c  pop     rdi
0x18007859d  pop     rsi
0x18007859e  pop     rbx
0x18007859f  pop     rbp
0x1800785a0  retn
```
