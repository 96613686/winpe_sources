# CddBitmapHw::SyncDXAccessInternal(void)

- ea: `0x14000e210`
- end: `0x14000e353`
- name: `?SyncDXAccessInternal@CddBitmapHw@@UEAAXXZ`
- size: `323`
- prototype: `void __fastcall(CddBitmapHw *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000e210`
- `0x14000e35c`
- `0x14000e420`
- `0x1400190c4`
- `0x140024cb4`
- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x14000e2be`
- `WIN32K!W32GetSessionState` at `0x14000e2be`

## pseudocode

```c
void __fastcall CddBitmapHw::SyncDXAccessInternal(CddBitmapHw *this)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // r14
  unsigned int (*v5)(void); // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  struct CDDPDEV *v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-48h]
  __int64 v12; // [rsp+30h] [rbp-40h]
  __int128 v13; // [rsp+38h] [rbp-38h] BYREF
  __int128 v14; // [rsp+48h] [rbp-28h]
  __int128 v15; // [rsp+58h] [rbp-18h]

  if ( *((_DWORD *)this + 10) )
  {
    v2 = *((_QWORD *)this + 1);
    v13 = 0;
    v3 = 0;
    v4 = 0;
    v14 = 0;
    v10 = 0;
    v15 = 0;
    v5 = *(unsigned int (**)(void))(v2 + 80);
    v12 = 0;
    if ( v5() )
    {
      v9 = (struct CDDPDEV *)*((_QWORD *)this + 1);
      v13 = 0;
      LODWORD(v13) = (_DWORD)this;
      v14 = 0;
      v15 = 0;
      CDDETWPROFILERSTARTEND::IssueStart((CDDETWPROFILERSTARTEND *)&v10, v9, 0xBECu, (struct _DXGKETW_PARAMS *)&v13);
      v4 = v12;
      v3 = v10;
    }
    if ( *((_BYTE *)this + 135)
      || !*(_DWORD *)(*(_QWORD *)(W32GetSessionState(v7, v6) + 72) + 3408LL)
      || (int)CDDSYNCOBJECT::IssueSignalForDxProcess((CddBitmapHw *)((char *)this + 208)) < 0
      || (int)CDDSYNCOBJECT::IssueWaitForGdi((CddBitmapHw *)((char *)this + 208)) < 0 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*((_QWORD *)this + 1) + 264LL))(3051, 0, 0);
      CDDPDEV::SyncGPUAccess(*((CDDPDEV **)this + 1), *((_DWORD *)this + 10), 1u);
      *((_BYTE *)this + 135) = 0;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)this + 1) + 392LL))(
        *(_QWORD *)(*((_QWORD *)this + 1) + 5472LL),
        *((unsigned int *)this + 10));
    }
    if ( v3 )
    {
      LOBYTE(v8) = 2;
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(v3 + 264))(v11, v8, v4);
    }
  }
}

```

## disassembly

```asm
0x14000e210  push    rbp
0x14000e212  push    rbx
0x14000e213  push    rsi
0x14000e214  push    rdi
0x14000e215  push    r14
0x14000e217  mov     rbp, rsp
0x14000e21a  sub     rsp, 70h
0x14000e21e  cmp     dword ptr [rcx+28h], 0
0x14000e222  mov     rbx, rcx
0x14000e225  jz      loc_14000E2B2
0x14000e22b  mov     rax, [rcx+8]
0x14000e22f  xorps   xmm0, xmm0
0x14000e232  movups  [rbp+var_38], xmm0
0x14000e236  xor     edi, edi
0x14000e238  xor     r14d, r14d
0x14000e23b  movups  [rbp+var_28], xmm0
0x14000e23f  mov     [rbp+var_50], rdi
0x14000e243  movups  [rbp+var_18], xmm0
0x14000e247  mov     rax, [rax+50h]
0x14000e24b  mov     [rbp+var_40], r14
0x14000e24f  call    _guard_dispatch_icall
0x14000e254  test    eax, eax
0x14000e256  jnz     loc_14000E31D
0x14000e25c  mov     al, [rbx+87h]
0x14000e262  test    al, al
0x14000e264  jz      short loc_14000E2BE
0x14000e266  mov     rax, [rbx+8]
0x14000e26a  xor     r8d, r8d
0x14000e26d  xor     edx, edx
0x14000e26f  mov     ecx, 0BEBh
0x14000e274  mov     rax, [rax+108h]
0x14000e27b  call    _guard_dispatch_icall
0x14000e280  mov     edx, [rbx+28h]; unsigned int
0x14000e283  mov     r8d, 1; int
0x14000e289  mov     rcx, [rbx+8]; this
0x14000e28d  call    ?SyncGPUAccess@CDDPDEV@@QEAAJIH@Z; CDDPDEV::SyncGPUAccess(uint,int)
0x14000e292  mov     byte ptr [rbx+87h], 0
0x14000e299  test    rdi, rdi
0x14000e29c  jz      short loc_14000E2B2
0x14000e29e  mov     rax, [rdi+108h]
0x14000e2a5  mov     r8, r14
0x14000e2a8  mov     ecx, [rbp+var_48]
0x14000e2ab  mov     dl, 2
0x14000e2ad  call    _guard_dispatch_icall
0x14000e2b2  add     rsp, 70h
0x14000e2b6  pop     r14
0x14000e2b8  pop     rdi
0x14000e2b9  pop     rsi
0x14000e2ba  pop     rbx
0x14000e2bb  pop     rbp
0x14000e2bc  retn
0x14000e2be  call    cs:__imp_W32GetSessionState
0x14000e2c5  nop     dword ptr [rax+rax+00h]
0x14000e2ca  mov     rcx, [rax+48h]
0x14000e2ce  cmp     dword ptr [rcx+0D50h], 0
0x14000e2d5  jz      short loc_14000E266
0x14000e2d7  lea     rsi, [rbx+0D0h]
0x14000e2de  mov     rcx, rsi; this
0x14000e2e1  call    ?IssueSignalForDxProcess@CDDSYNCOBJECT@@QEAAJXZ; CDDSYNCOBJECT::IssueSignalForDxProcess(void)
0x14000e2e6  test    eax, eax
0x14000e2e8  js      loc_14000E266
0x14000e2ee  mov     rcx, rsi; this
0x14000e2f1  call    ?IssueWaitForGdi@CDDSYNCOBJECT@@QEAAJXZ; CDDSYNCOBJECT::IssueWaitForGdi(void)
0x14000e2f6  test    eax, eax
0x14000e2f8  js      loc_14000E266
0x14000e2fe  mov     rcx, [rbx+8]
0x14000e302  mov     edx, [rbx+28h]
0x14000e305  mov     rax, [rcx+188h]
0x14000e30c  mov     rcx, [rcx+1560h]
0x14000e313  call    _guard_dispatch_icall
0x14000e318  jmp     loc_14000E299
0x14000e31d  mov     rdx, [rbx+8]; struct CDDPDEV *
0x14000e321  lea     r9, [rbp+var_38]; struct _DXGKETW_PARAMS *
0x14000e325  xorps   xmm0, xmm0
0x14000e328  lea     rcx, [rbp+var_50]; this
0x14000e32c  movups  [rbp+var_38], xmm0
0x14000e330  mov     r8d, 0BECh; unsigned int
0x14000e336  mov     dword ptr [rbp+var_38], ebx
0x14000e339  movups  [rbp+var_28], xmm0
0x14000e33d  movups  [rbp+var_18], xmm0
0x14000e341  call    ?IssueStart@CDDETWPROFILERSTARTEND@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@@Z; CDDETWPROFILERSTARTEND::IssueStart(CDDPDEV *,uint,_DXGKETW_PARAMS *)
0x14000e346  mov     r14, [rbp+var_40]
0x14000e34a  mov     rdi, [rbp+var_50]
0x14000e34e  jmp     loc_14000E25C
```
