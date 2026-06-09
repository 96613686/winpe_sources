# CDXGIOutput::GetMultiplaneOverlayCapsInternal(IUnknown *,int *,DXGI_MULTIPLANE_OVERLAY_CAPS *)

- ea: `0x1800142d0`
- end: `0x18001457f`
- name: `?GetMultiplaneOverlayCapsInternal@CDXGIOutput@@QEAAJPEAUIUnknown@@PEAHPEAUDXGI_MULTIPLANE_OVERLAY_CAPS@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(CDXGIOutput *__hidden this, struct IUnknown *, int *, struct DXGI_MULTIPLANE_OVERLAY_CAPS *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180013ae0`
- `0x180015c60`
- `0x1800256a0`

## callees

- `0x18000cb70`
- `0x1800142d0`
- `0x180014590`
- `0x1800145b0`
- `0x18001466c`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-dx-d3dkmt-l1-1-3!D3DKMTGetMultiPlaneOverlayCaps` at `0x180014364`
- `api-ms-win-dx-d3dkmt-l1-1-3!D3DKMTGetMultiPlaneOverlayCaps` at `0x180014364`
- `api-ms-win-dx-d3dkmt-l1-1-3!D3DKMTGetPostCompositionCaps` at `0x180014447`
- `api-ms-win-dx-d3dkmt-l1-1-3!D3DKMTGetPostCompositionCaps` at `0x180014447`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDXGIOutput::GetMultiplaneOverlayCapsInternal(
        CDXGIOutput *this,
        struct IUnknown *a2,
        int *a3,
        struct DXGI_MULTIPLANE_OVERLAY_CAPS *a4)
{
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ecx
  int v15; // r9d
  unsigned int v16; // edx
  int v17; // r8d
  int v18; // eax
  int v19; // xmm0_4
  __int128 v20; // [rsp+30h] [rbp-40h] BYREF
  __int128 v21; // [rsp+40h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h]

  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *(_OWORD *)((char *)a4 + 28) = 0;
  *(_DWORD *)a4 = 1;
  *((_DWORD *)a4 + 4) = 1065353216;
  *((_DWORD *)a4 + 5) = 1065353216;
  *a3 = 0;
  v8 = 0;
  if ( CDXGIOutput::IsMPOAllowed(this) )
  {
    if ( CDXGIOutput::DriverSupportsKernelOverlayCaps(this) )
    {
      v21 = 0;
      v22 = 0;
      LODWORD(v21) = CDXGIOutput::GetAdapterHandle(this);
      DWORD1(v21) = *((_DWORD *)this + 64);
      v9 = D3DKMTGetMultiPlaneOverlayCaps(&v21);
      v10 = NTStatusToHResult(v9);
      v8 = v10;
      if ( v10 == -2005530512 )
        return (unsigned int)-2005270523;
      if ( v10 < 0 )
        return (unsigned int)v8;
      v20 = 0;
      LODWORD(v20) = CDXGIOutput::GetAdapterHandle(this);
      DWORD1(v20) = *((_DWORD *)this + 64);
      v12 = D3DKMTGetPostCompositionCaps(&v20);
      v13 = NTStatusToHResult(v12);
      v8 = v13;
      if ( v13 == -2005530512 )
      {
        return (unsigned int)-2005270523;
      }
      else if ( v13 >= 0 )
      {
        *(_DWORD *)a4 = DWORD2(v21);
        v14 = HIDWORD(v21);
        *((_DWORD *)a4 + 1) = HIDWORD(v21);
        v15 = v22;
        *((_DWORD *)a4 + 2) = v22;
        *((_QWORD *)a4 + 2) = *((_QWORD *)&v22 + 1);
        v16 = DWORD1(v22);
        v17 = BYTE4(v22) & 1
            | (((DWORD1(v22) >> 1) & 1) << 15)
            | (2 * ((DWORD1(v22) >> 2) & 1))
            | (4 * ((DWORD1(v22) >> 3) & 1))
            | (((DWORD1(v22) >> 9) & 1) << 16)
            | (((DWORD1(v22) >> 10) & 1) << 17)
            | (((DWORD1(v22) >> 11) & 1) << 18)
            | (((DWORD1(v22) >> 6) & 1) << 7)
            | (((DWORD1(v22) >> 7) & 1) << 8)
            | (((DWORD1(v22) >> 8) & 1) << 13);
        *((_DWORD *)a4 + 3) = v17;
        if ( v14 <= 1 )
        {
          v18 = v17;
        }
        else
        {
          v18 = v17 | (((v16 >> 4) & 1) << 10) | 0x20;
          *((_DWORD *)a4 + 3) = v18;
        }
        if ( v15 )
          *((_DWORD *)a4 + 3) = v18 | (((v16 >> 5) & 1) << 9) | 0x40;
        v19 = DWORD2(v20);
        if ( *((float *)&v20 + 2) > 1.0 )
        {
          *((_DWORD *)a4 + 6) = 1;
          *((_DWORD *)a4 + 8) = 1024;
          *((_DWORD *)a4 + 9) = v19;
          *((_DWORD *)a4 + 10) = HIDWORD(v20);
        }
        *a3 = 1;
      }
    }
    else if ( a2 )
    {
      *(_QWORD *)&v20 = 0;
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int128 *))a2->lpVtbl->QueryInterface)(
             a2,
             &GUID_b898d4fd_b5b3_4ffc_8694_0259864ffcf8,
             &v20);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct DXGI_MULTIPLANE_OVERLAY_CAPS *, int *))(*(_QWORD *)v20 + 216LL))(
               v20,
               *((unsigned int *)this + 64),
               a4,
               a3);
        if ( (_QWORD)v20 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
      }
      else if ( (_QWORD)v20 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800142d0  push    rbp
0x1800142d2  push    rbx
0x1800142d3  push    rsi
0x1800142d4  push    rdi
0x1800142d5  push    r12
0x1800142d7  push    r14
0x1800142d9  push    r15
0x1800142db  mov     rbp, rsp
0x1800142de  sub     rsp, 70h
0x1800142e2  mov     rax, cs:__security_cookie
0x1800142e9  xor     rax, rsp
0x1800142ec  mov     [rbp+var_10], rax
0x1800142f0  mov     rdi, r9
0x1800142f3  mov     r15, r8
0x1800142f6  mov     r14, rdx
0x1800142f9  mov     rsi, rcx
0x1800142fc  xorps   xmm0, xmm0
0x1800142ff  movups  xmmword ptr [r9], xmm0
0x180014303  movups  xmmword ptr [r9+10h], xmm0
0x180014308  movups  xmmword ptr [r9+1Ch], xmm0
0x18001430d  mov     r12d, 1
0x180014313  mov     [r9], r12d
0x180014316  mov     eax, 3F800000h
0x18001431b  mov     [r9+10h], eax
0x18001431f  mov     [r9+14h], eax
0x180014323  mov     dword ptr [r8], 0
0x18001432a  xor     ebx, ebx
0x18001432c  call    ?IsMPOAllowed@CDXGIOutput@@QEAA_NXZ; CDXGIOutput::IsMPOAllowed(void)
0x180014331  test    al, al
0x180014333  jz      short loc_180014387
0x180014335  mov     rcx, rsi; this
0x180014338  call    ?DriverSupportsKernelOverlayCaps@CDXGIOutput@@QEAA_NXZ; CDXGIOutput::DriverSupportsKernelOverlayCaps(void)
0x18001433d  test    al, al
0x18001433f  jz      short loc_1800143A4
0x180014341  xorps   xmm0, xmm0
0x180014344  movups  [rbp+var_30], xmm0
0x180014348  movups  [rbp+var_20], xmm0
0x18001434c  mov     rcx, rsi; this
0x18001434f  call    ?GetAdapterHandle@CDXGIOutput@@QEBAIXZ; CDXGIOutput::GetAdapterHandle(void)
0x180014354  mov     dword ptr [rbp+var_30], eax
0x180014357  mov     eax, [rsi+100h]
0x18001435d  mov     dword ptr [rbp+var_30+4], eax
0x180014360  lea     rcx, [rbp+var_30]
0x180014364  call    cs:__imp_D3DKMTGetMultiPlaneOverlayCaps
0x18001436a  mov     ecx, eax; int
0x18001436c  call    ?NTStatusToHResult@@YAJJ@Z; NTStatusToHResult(long)
0x180014371  mov     ebx, eax
0x180014373  mov     r14d, 88760870h
0x180014379  cmp     eax, r14d
0x18001437c  jnz     loc_180014420
0x180014382  mov     ebx, 887A0005h
0x180014387  mov     eax, ebx
0x180014389  mov     rcx, [rbp+var_10]
0x18001438d  xor     rcx, rsp; StackCookie
0x180014390  call    __security_check_cookie
0x180014395  add     rsp, 70h
0x180014399  pop     r15
0x18001439b  pop     r14
0x18001439d  pop     r12
0x18001439f  pop     rdi
0x1800143a0  pop     rsi
0x1800143a1  pop     rbx
0x1800143a2  pop     rbp
0x1800143a3  retn
0x1800143a4  test    r14, r14
0x1800143a7  jz      short loc_180014387
0x1800143a9  mov     qword ptr [rbp+var_40], rbx
0x1800143ad  mov     rax, [r14]
0x1800143b0  lea     r8, [rbp+var_40]
0x1800143b4  lea     rdx, _GUID_b898d4fd_b5b3_4ffc_8694_0259864ffcf8
0x1800143bb  mov     rcx, r14
0x1800143be  mov     rax, [rax]
0x1800143c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c6  mov     ebx, eax
0x1800143c8  test    eax, eax
0x1800143ca  jns     short loc_1800143E4
0x1800143cc  mov     rcx, qword ptr [rbp+var_40]
0x1800143d0  test    rcx, rcx
0x1800143d3  jz      short loc_1800143E2
0x1800143d5  mov     rdx, [rcx]
0x1800143d8  mov     rax, [rdx+10h]
0x1800143dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e1  nop
0x1800143e2  jmp     short loc_180014387
0x1800143e4  mov     rcx, qword ptr [rbp+var_40]
0x1800143e8  mov     rax, [rcx]
0x1800143eb  mov     r9, r15
0x1800143ee  mov     r8, rdi
0x1800143f1  mov     edx, [rsi+100h]
0x1800143f7  mov     rax, [rax+0D8h]
0x1800143fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014403  mov     ebx, eax
0x180014405  mov     rcx, qword ptr [rbp+var_40]
0x180014409  test    rcx, rcx
0x18001440c  jz      short loc_18001441B
0x18001440e  mov     rdx, [rcx]
0x180014411  mov     rax, [rdx+10h]
0x180014415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001441a  nop
0x18001441b  jmp     loc_180014387
0x180014420  test    eax, eax
0x180014422  js      loc_180014387
0x180014428  xorps   xmm0, xmm0
0x18001442b  movups  [rbp+var_40], xmm0
0x18001442f  mov     rcx, rsi; this
0x180014432  call    ?GetAdapterHandle@CDXGIOutput@@QEBAIXZ; CDXGIOutput::GetAdapterHandle(void)
0x180014437  mov     dword ptr [rbp+var_40], eax
0x18001443a  mov     eax, [rsi+100h]
0x180014440  mov     dword ptr [rbp+var_40+4], eax
0x180014443  lea     rcx, [rbp+var_40]
0x180014447  call    cs:__imp_D3DKMTGetPostCompositionCaps
0x18001444d  mov     ecx, eax; int
0x18001444f  call    ?NTStatusToHResult@@YAJJ@Z; NTStatusToHResult(long)
0x180014454  mov     ebx, eax
0x180014456  cmp     eax, r14d
0x180014459  jz      loc_180014382
0x18001445f  test    eax, eax
0x180014461  js      loc_180014387
0x180014467  mov     eax, dword ptr [rbp+var_30+8]
0x18001446a  mov     [rdi], eax
0x18001446c  mov     ecx, dword ptr [rbp+var_30+0Ch]
0x18001446f  mov     [rdi+4], ecx
0x180014472  mov     r9d, dword ptr [rbp+var_20]
0x180014476  mov     [rdi+8], r9d
0x18001447a  movss   xmm0, dword ptr [rbp+var_20+8]
0x18001447f  movss   dword ptr [rdi+10h], xmm0
0x180014484  movss   xmm1, dword ptr [rbp+var_20+0Ch]
0x180014489  movss   dword ptr [rdi+14h], xmm1
0x18001448e  mov     edx, dword ptr [rbp+var_20+4]
0x180014491  mov     r8d, edx
0x180014494  shr     r8d, 8
0x180014498  and     r8d, r12d
0x18001449b  shl     r8d, 0Dh
0x18001449f  mov     eax, edx
0x1800144a1  shr     eax, 7
0x1800144a4  and     eax, r12d
0x1800144a7  shl     eax, 8
0x1800144aa  or      r8d, eax
0x1800144ad  mov     eax, edx
0x1800144af  shr     eax, 6
0x1800144b2  and     eax, r12d
0x1800144b5  shl     eax, 7
0x1800144b8  or      r8d, eax
0x1800144bb  mov     eax, edx
0x1800144bd  shr     eax, 0Bh
0x1800144c0  and     eax, r12d
0x1800144c3  shl     eax, 12h
0x1800144c6  or      r8d, eax
0x1800144c9  mov     eax, edx
0x1800144cb  shr     eax, 0Ah
0x1800144ce  and     eax, r12d
0x1800144d1  shl     eax, 11h
0x1800144d4  or      r8d, eax
0x1800144d7  mov     eax, edx
0x1800144d9  shr     eax, 9
0x1800144dc  and     eax, r12d
0x1800144df  shl     eax, 10h
0x1800144e2  or      r8d, eax
0x1800144e5  mov     eax, edx
0x1800144e7  shr     eax, 3
0x1800144ea  and     eax, r12d
0x1800144ed  shl     eax, 2
0x1800144f0  or      r8d, eax
0x1800144f3  mov     eax, edx
0x1800144f5  shr     eax, 2
0x1800144f8  and     eax, r12d
0x1800144fb  add     eax, eax
0x1800144fd  or      r8d, eax
0x180014500  mov     eax, edx
0x180014502  shr     eax, 1
0x180014504  and     eax, r12d
0x180014507  shl     eax, 0Fh
0x18001450a  or      r8d, eax
0x18001450d  mov     eax, edx
0x18001450f  and     eax, r12d
0x180014512  or      r8d, eax
0x180014515  mov     [rdi+0Ch], r8d
0x180014519  cmp     ecx, r12d
0x18001451c  jbe     short loc_180014567
0x18001451e  mov     eax, edx
0x180014520  shr     eax, 4
0x180014523  and     eax, r12d
0x180014526  shl     eax, 0Ah
0x180014529  or      eax, r8d
0x18001452c  or      eax, 20h
0x18001452f  mov     [rdi+0Ch], eax
0x180014532  test    r9d, r9d
0x180014535  jnz     short loc_18001456C
0x180014537  movss   xmm0, dword ptr [rbp+var_40+8]
0x18001453c  comiss  xmm0, cs:__real@3f800000
0x180014543  jbe     short loc_18001455F
0x180014545  mov     [rdi+18h], r12d
0x180014549  mov     dword ptr [rdi+20h], 400h
0x180014550  movss   dword ptr [rdi+24h], xmm0
0x180014555  movss   xmm0, dword ptr [rbp+var_40+0Ch]
0x18001455a  movss   dword ptr [rdi+28h], xmm0
0x18001455f  mov     [r15], r12d
0x180014562  jmp     loc_180014387
0x180014567  mov     eax, r8d
0x18001456a  jmp     short loc_180014532
0x18001456c  shr     edx, 5
0x18001456f  and     edx, r12d
0x180014572  shl     edx, 9
0x180014575  or      edx, eax
0x180014577  or      edx, 40h
0x18001457a  mov     [rdi+0Ch], edx
0x18001457d  jmp     short loc_180014537
```
