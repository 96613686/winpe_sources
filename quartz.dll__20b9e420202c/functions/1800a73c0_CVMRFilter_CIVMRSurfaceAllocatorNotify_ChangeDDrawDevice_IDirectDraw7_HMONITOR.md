# CVMRFilter::CIVMRSurfaceAllocatorNotify::ChangeDDrawDevice(IDirectDraw7 *,HMONITOR__ *)

- ea: `0x1800a73c0`
- end: `0x1800a759e`
- name: `?ChangeDDrawDevice@CIVMRSurfaceAllocatorNotify@CVMRFilter@@UEAAJPEAUIDirectDraw7@@PEAUHMONITOR__@@@Z`
- size: `478`
- prototype: `int(CVMRFilter::CIVMRSurfaceAllocatorNotify *__hidden this, struct IDirectDraw7 *, HMONITOR)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800300cc`
- `0x1800388a0`
- `0x180039250`
- `0x1800a73c0`
- `0x1800aa3a0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800a7564`
- `KERNEL32!LeaveCriticalSection` at `0x1800a7564`
- `KERNEL32!EnterCriticalSection` at `0x1800a73fd`
- `KERNEL32!EnterCriticalSection` at `0x1800a73fd`
- `ole32!CoTaskMemFree` at `0x1800a7528`
- `ole32!CoTaskMemFree` at `0x1800a7528`
- `ole32!CoTaskMemAlloc` at `0x1800a744b`
- `ole32!CoTaskMemAlloc` at `0x1800a744b`

## pseudocode

```c
__int64 __fastcall CVMRFilter::CIVMRSurfaceAllocatorNotify::ChangeDDrawDevice(
        CVMRFilter::CIVMRSurfaceAllocatorNotify *this,
        struct IDirectDraw7 *a2,
        HMONITOR a3)
{
  __int64 v3; // rbx
  int v7; // ebp
  int v8; // edi
  _QWORD *v9; // rax
  _QWORD *v10; // r12
  int v11; // r13d
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rax
  int i; // edi
  __int64 v19; // rcx
  int v21; // [rsp+20h] [rbp-D8h]
  _QWORD v22[16]; // [rsp+30h] [rbp-C8h] BYREF

  v3 = *((_QWORD *)this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 376));
  v7 = CVMRFilter::SetDDrawDeviceWorker(*((CVMRFilter **)this + 2), a2, a3);
  if ( v7 >= 0 )
  {
    memset_0(v22, 0, sizeof(v22));
    v8 = *(_DWORD *)(*((_QWORD *)this + 2) + 572LL);
    v21 = v8;
    v9 = CoTaskMemAlloc((unsigned int)(8 * v8));
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, (unsigned int)(8 * v8));
      v11 = 0;
      v12 = 0;
      if ( v8 <= 0 )
        goto LABEL_12;
      do
      {
        if ( !v7 )
        {
          v13 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v12 + 248);
          if ( *(_QWORD *)(v13 + 48) )
          {
            v14 = v11;
            v15 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))(v13 + 24))(
                    v13 + 24,
                    &IID_IPin,
                    (__int64)&v10[v11]);
            v16 = *((_QWORD *)this + 2);
            v7 = v15;
            v17 = v10[v11++];
            v8 = v21;
            v22[v14] = v17;
            *(_DWORD *)(v16 + 1044) |= 1 << *(_DWORD *)(*(_QWORD *)(v16 + 8 * v12 + 248) + 728LL);
          }
        }
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (int)v12 < v8 );
      if ( v11 <= 0 )
      {
LABEL_12:
        CoTaskMemFree(v10);
      }
      else
      {
        CBaseFilter::NotifyEvent(*((CBaseFilter **)this + 2), 22, (__int64)v10, v11);
        for ( i = 0; i < v11; ++i )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22[i] + 16LL))(v22[i]);
      }
      if ( v7 >= 0 )
      {
        v19 = *(_QWORD *)(*((_QWORD *)this + 2) + 496LL);
        if ( v19 )
          v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 64LL))(v19);
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 376));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a73c0  mov     [rsp+arg_18], rbx
0x1800a73c5  push    rbp
0x1800a73c6  push    rsi
0x1800a73c7  push    rdi
0x1800a73c8  push    r12
0x1800a73ca  push    r13
0x1800a73cc  push    r14
0x1800a73ce  push    r15
0x1800a73d0  sub     rsp, 0C0h
0x1800a73d7  mov     rax, cs:__security_cookie
0x1800a73de  xor     rax, rsp
0x1800a73e1  mov     [rsp+0F8h+var_48], rax
0x1800a73e9  mov     rbx, [rcx+10h]
0x1800a73ed  mov     r14, rcx
0x1800a73f0  mov     rsi, r8
0x1800a73f3  mov     rdi, rdx
0x1800a73f6  lea     rcx, [rbx+178h]; lpCriticalSection
0x1800a73fd  call    cs:__imp_EnterCriticalSection
0x1800a7404  nop     dword ptr [rax+rax+00h]
0x1800a7409  mov     rcx, [r14+10h]; this
0x1800a740d  mov     r8, rsi; HMONITOR
0x1800a7410  mov     rdx, rdi; struct IDirectDraw7 *
0x1800a7413  call    ?SetDDrawDeviceWorker@CVMRFilter@@AEAAJPEAUIDirectDraw7@@PEAUHMONITOR__@@@Z; CVMRFilter::SetDDrawDeviceWorker(IDirectDraw7 *,HMONITOR__ *)
0x1800a7418  mov     ebp, eax
0x1800a741a  test    eax, eax
0x1800a741c  js      loc_1800A755D
0x1800a7422  xor     edx, edx; Val
0x1800a7424  lea     rcx, [rsp+0F8h+var_C8]; void *
0x1800a7429  mov     r8d, 80h; Size
0x1800a742f  call    memset_0
0x1800a7434  mov     rcx, [r14+10h]
0x1800a7438  mov     edi, [rcx+23Ch]
0x1800a743e  mov     [rsp+0F8h+var_D8], edi
0x1800a7442  lea     ecx, ds:0[rdi*8]; cb
0x1800a7449  mov     esi, ecx
0x1800a744b  call    cs:__imp_CoTaskMemAlloc
0x1800a7452  nop     dword ptr [rax+rax+00h]
0x1800a7457  mov     r12, rax
0x1800a745a  test    rax, rax
0x1800a745d  jz      loc_1800A7558
0x1800a7463  mov     r8d, esi; Size
0x1800a7466  xor     edx, edx; Val
0x1800a7468  mov     rcx, rax; void *
0x1800a746b  call    memset_0
0x1800a7470  xor     r13d, r13d
0x1800a7473  xor     r15d, r15d
0x1800a7476  test    edi, edi
0x1800a7478  jle     loc_1800A7525
0x1800a747e  test    ebp, ebp
0x1800a7480  jnz     short loc_1800A74E5
0x1800a7482  mov     rax, [r14+10h]
0x1800a7486  mov     rcx, [rax+r15*8+0F8h]
0x1800a748e  cmp     qword ptr [rcx+30h], 0
0x1800a7493  jz      short loc_1800A74E5
0x1800a7495  add     rcx, 18h
0x1800a7499  movsxd  rsi, r13d
0x1800a749c  lea     rdx, IID_IPin
0x1800a74a3  mov     rax, [rcx]
0x1800a74a6  lea     rdi, [r12+rsi*8]
0x1800a74aa  mov     r8, rdi
0x1800a74ad  mov     rax, [rax]
0x1800a74b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a74b5  mov     rdx, [r14+10h]
0x1800a74b9  mov     ebp, eax
0x1800a74bb  mov     rax, [rdi]
0x1800a74be  inc     r13d
0x1800a74c1  mov     edi, [rsp+0F8h+var_D8]
0x1800a74c5  mov     [rsp+rsi*8+0F8h+var_C8], rax
0x1800a74ca  mov     eax, 1
0x1800a74cf  mov     rcx, [rdx+r15*8+0F8h]
0x1800a74d7  mov     ecx, [rcx+2D8h]
0x1800a74dd  shl     eax, cl
0x1800a74df  or      [rdx+414h], eax
0x1800a74e5  inc     r15d
0x1800a74e8  cmp     r15d, edi
0x1800a74eb  jl      short loc_1800A747E
0x1800a74ed  test    r13d, r13d
0x1800a74f0  jle     short loc_1800A7525
0x1800a74f2  mov     rcx, [r14+10h]; this
0x1800a74f6  mov     r8, r12; __int64
0x1800a74f9  movsxd  r9, r13d; __int64
0x1800a74fc  mov     edx, 16h; int
0x1800a7501  call    ?NotifyEvent@CBaseFilter@@QEAAJJ_J0@Z; CBaseFilter::NotifyEvent(long,__int64,__int64)
0x1800a7506  xor     edi, edi
0x1800a7508  movsxd  rax, edi
0x1800a750b  mov     rcx, [rsp+rax*8+0F8h+var_C8]
0x1800a7510  mov     rax, [rcx]
0x1800a7513  mov     rax, [rax+10h]
0x1800a7517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a751c  inc     edi
0x1800a751e  cmp     edi, r13d
0x1800a7521  jl      short loc_1800A7508
0x1800a7523  jmp     short loc_1800A7534
0x1800a7525  mov     rcx, r12; pv
0x1800a7528  call    cs:__imp_CoTaskMemFree
0x1800a752f  nop     dword ptr [rax+rax+00h]
0x1800a7534  test    ebp, ebp
0x1800a7536  js      short loc_1800A755D
0x1800a7538  mov     rax, [r14+10h]
0x1800a753c  mov     rcx, [rax+1F0h]
0x1800a7543  test    rcx, rcx
0x1800a7546  jz      short loc_1800A755D
0x1800a7548  mov     rax, [rcx]
0x1800a754b  mov     rax, [rax+40h]
0x1800a754f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7554  mov     ebp, eax
0x1800a7556  jmp     short loc_1800A755D
0x1800a7558  mov     ebp, 8007000Eh
0x1800a755d  lea     rcx, [rbx+178h]; lpCriticalSection
0x1800a7564  call    cs:__imp_LeaveCriticalSection
0x1800a756b  nop     dword ptr [rax+rax+00h]
0x1800a7570  mov     eax, ebp
0x1800a7572  mov     rcx, [rsp+0F8h+var_48]
0x1800a757a  xor     rcx, rsp; StackCookie
0x1800a757d  call    __security_check_cookie
0x1800a7582  mov     rbx, [rsp+0F8h+arg_18]
0x1800a758a  add     rsp, 0C0h
0x1800a7591  pop     r15
0x1800a7593  pop     r14
0x1800a7595  pop     r13
0x1800a7597  pop     r12
0x1800a7599  pop     rdi
0x1800a759a  pop     rsi
0x1800a759b  pop     rbp
0x1800a759c  retn
```
