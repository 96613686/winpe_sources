# CACMWrapper::SendExtraStuff(void)

- ea: `0x180120184`
- end: `0x1801203c6`
- name: `?SendExtraStuff@CACMWrapper@@QEAAJXZ`
- size: `578`
- prototype: `__int64 __fastcall(CACMWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800233b0`
- `0x18011f4a0`

## callees

- `0x1800208d8`
- `0x180120184`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1801203ae`
- `KERNEL32!LeaveCriticalSection` at `0x1801203ae`
- `KERNEL32!EnterCriticalSection` at `0x1801201b4`
- `KERNEL32!EnterCriticalSection` at `0x1801201b4`
- `ole32!CoTaskMemRealloc` at `0x18012027c`
- `ole32!CoTaskMemRealloc` at `0x18012027c`
- `ole32!CoTaskMemFree` at `0x180120301`
- `ole32!CoTaskMemFree` at `0x180120301`

## pseudocode

```c
__int64 __fastcall CACMWrapper::SendExtraStuff(CACMWrapper *this)
{
  bool v1; // zf
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rcx
  int v6; // edi
  __int64 v7; // rdi
  LPVOID v8; // rax
  int v9; // r8d
  unsigned __int8 *v10; // rdx
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  __int64 v15; // [rsp+48h] [rbp-10h] BYREF
  int v16; // [rsp+80h] [rbp+28h] BYREF
  int v17; // [rsp+88h] [rbp+30h] BYREF
  int v18; // [rsp+90h] [rbp+38h] BYREF
  struct IMediaSample *v19; // [rsp+98h] [rbp+40h] BYREF

  v1 = *((_DWORD *)this + 78) == 0;
  v16 = 0;
  if ( v1 )
    return 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  v5 = *((_QWORD *)this + 28);
  v19 = 0;
  v15 = 0;
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, struct IMediaSample **, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v5 + 128LL))(
         v5,
         &v19,
         0,
         0,
         0);
  if ( v6 >= 0 )
  {
    v7 = 1;
    ((void (__fastcall *)(struct IMediaSample *, __int64))v19->lpVtbl->SetSyncPoint)(v19, 1);
    ((void (__fastcall *)(struct IMediaSample *, _QWORD))v19->lpVtbl->SetDiscontinuity)(v19, 0);
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, int *, __int64))qword_18019E8C8)(
                          *((_QWORD *)this + 32),
                          *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 28) + 184LL) + 12LL),
                          &v16,
                          1)
      && *((_DWORD *)this + 78) < v16 )
    {
      v8 = CoTaskMemRealloc(*((LPVOID *)this + 38), v16);
      if ( !v8 )
      {
        ((void (__fastcall *)(struct IMediaSample *))v19->lpVtbl->Release)(v19);
        v6 = -2147024882;
        goto LABEL_14;
      }
      *((_QWORD *)this + 38) = v8;
    }
    v9 = *((_DWORD *)this + 78);
    v10 = (unsigned __int8 *)*((_QWORD *)this + 38);
    v18 = 0;
    v17 = 0;
    CACMWrapper::ProcessSample(this, v10, v9, v19, &v18, &v17, 0);
    v11 = (void *)*((_QWORD *)this + 38);
    *((_DWORD *)this + 78) = 0;
    CoTaskMemFree(v11);
    v12 = v17;
    *((_QWORD *)this + 38) = 0;
    if ( (_DWORD)v12 )
    {
      v13 = *((unsigned int *)this + 70);
      v15 = *((_QWORD *)this + 34) - *((_QWORD *)this + 40);
      if ( v13 + v15 )
        v7 = 10000000 * v12 / v13;
      v14 = v7;
      ((void (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))v19->lpVtbl->SetTime)(v19, &v15, &v14);
      (*(void (__fastcall **)(_QWORD, struct IMediaSample *))(**((_QWORD **)this + 28) + 136LL))(
        *((_QWORD *)this + 28),
        v19);
      ((void (__fastcall *)(struct IMediaSample *))v19->lpVtbl->Release)(v19);
      v6 = 0;
    }
    else
    {
      ((void (__fastcall *)(struct IMediaSample *))v19->lpVtbl->Release)(v19);
      v6 = -2147467259;
    }
  }
LABEL_14:
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180120184  push    rbp
0x180120186  push    rbx
0x180120187  push    rsi
0x180120188  push    rdi
0x180120189  mov     rbp, rsp
0x18012018c  sub     rsp, 58h
0x180120190  cmp     dword ptr [rcx+138h], 0
0x180120197  mov     rbx, rcx
0x18012019a  mov     [rbp+arg_0], 0
0x1801201a1  jnz     short loc_1801201AA
0x1801201a3  xor     eax, eax
0x1801201a5  jmp     loc_1801203BC
0x1801201aa  lea     rsi, [rcx+148h]
0x1801201b1  mov     rcx, rsi; lpCriticalSection
0x1801201b4  call    cs:__imp_EnterCriticalSection
0x1801201bb  nop     dword ptr [rax+rax+00h]
0x1801201c0  mov     rcx, [rbx+0E0h]
0x1801201c7  lea     rdx, [rbp+arg_18]
0x1801201cb  mov     [rbp+arg_18], 0
0x1801201d3  xor     r9d, r9d
0x1801201d6  mov     [rbp+var_10], 0
0x1801201de  xor     r8d, r8d
0x1801201e1  mov     [rbp+var_18], 0
0x1801201e9  mov     rax, [rcx]
0x1801201ec  mov     dword ptr [rsp+58h+var_38], 0
0x1801201f4  mov     rax, [rax+80h]
0x1801201fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120200  mov     edi, eax
0x180120202  test    eax, eax
0x180120204  js      loc_1801203AB
0x18012020a  mov     rcx, [rbp+arg_18]
0x18012020e  mov     edi, 1
0x180120213  mov     edx, edi
0x180120215  mov     rax, [rcx]
0x180120218  mov     rax, [rax+40h]
0x18012021c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120221  mov     rcx, [rbp+arg_18]
0x180120225  xor     edx, edx
0x180120227  mov     rax, [rcx]
0x18012022a  mov     rax, [rax+80h]
0x180120231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120236  mov     rcx, [rbx+0E0h]
0x18012023d  lea     r8, [rbp+arg_0]
0x180120241  mov     rax, cs:qword_18019E8C8
0x180120248  mov     r9d, edi
0x18012024b  mov     rdx, [rcx+0B8h]
0x180120252  mov     rcx, [rbx+100h]
0x180120259  movzx   edx, word ptr [rdx+0Ch]
0x18012025d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120262  test    eax, eax
0x180120264  jnz     short loc_1801202AE
0x180120266  movsxd  rax, [rbp+arg_0]
0x18012026a  cmp     [rbx+138h], eax
0x180120270  jge     short loc_1801202AE
0x180120272  mov     rcx, [rbx+130h]; pv
0x180120279  mov     rdx, rax; cb
0x18012027c  call    cs:__imp_CoTaskMemRealloc
0x180120283  nop     dword ptr [rax+rax+00h]
0x180120288  test    rax, rax
0x18012028b  jnz     short loc_1801202A7
0x18012028d  mov     rcx, [rbp+arg_18]
0x180120291  mov     rax, [rcx]
0x180120294  mov     rax, [rax+10h]
0x180120298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012029d  mov     edi, 8007000Eh
0x1801202a2  jmp     loc_1801203AB
0x1801202a7  mov     [rbx+130h], rax
0x1801202ae  mov     r9, [rbp+arg_18]; struct IMediaSample *
0x1801202b2  lea     rax, [rbp+arg_8]
0x1801202b6  mov     r8d, [rbx+138h]; int
0x1801202bd  mov     rcx, rbx; this
0x1801202c0  mov     rdx, [rbx+130h]; unsigned __int8 *
0x1801202c7  mov     [rsp+58h+var_28], 0; int
0x1801202cf  mov     [rsp+58h+var_30], rax; int *
0x1801202d4  lea     rax, [rbp+arg_10]
0x1801202d8  mov     [rsp+58h+var_38], rax; int *
0x1801202dd  mov     [rbp+arg_10], 0
0x1801202e4  mov     [rbp+arg_8], 0
0x1801202eb  call    ?ProcessSample@CACMWrapper@@QEAAJPEAEJPEAUIMediaSample@@PEAJ2H@Z; CACMWrapper::ProcessSample(uchar *,long,IMediaSample *,long *,long *,int)
0x1801202f0  mov     rcx, [rbx+130h]; pv
0x1801202f7  mov     dword ptr [rbx+138h], 0
0x180120301  call    cs:__imp_CoTaskMemFree
0x180120308  nop     dword ptr [rax+rax+00h]
0x18012030d  movsxd  rdx, [rbp+arg_8]
0x180120311  mov     qword ptr [rbx+130h], 0
0x18012031c  test    edx, edx
0x18012031e  jnz     short loc_180120337
0x180120320  mov     rcx, [rbp+arg_18]
0x180120324  mov     rax, [rcx]
0x180120327  mov     rax, [rax+10h]
0x18012032b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120330  mov     edi, 80004005h
0x180120335  jmp     short loc_1801203AB
0x180120337  mov     rax, [rbx+110h]
0x18012033e  sub     rax, [rbx+140h]
0x180120345  mov     ecx, [rbx+118h]
0x18012034b  mov     [rbp+var_10], rax
0x18012034f  add     rax, rcx
0x180120352  jz      short loc_180120363
0x180120354  imul    rax, rdx, 989680h
0x18012035b  cqo
0x18012035d  idiv    rcx
0x180120360  mov     rdi, rax
0x180120363  mov     rcx, [rbp+arg_18]
0x180120367  lea     r8, [rbp+var_18]
0x18012036b  mov     [rbp+var_18], rdi
0x18012036f  lea     rdx, [rbp+var_10]
0x180120373  mov     rax, [rcx]
0x180120376  mov     rax, [rax+30h]
0x18012037a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012037f  mov     rcx, [rbx+0E0h]
0x180120386  mov     rdx, [rbp+arg_18]
0x18012038a  mov     rax, [rcx]
0x18012038d  mov     rax, [rax+88h]
0x180120394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120399  mov     rcx, [rbp+arg_18]
0x18012039d  mov     rax, [rcx]
0x1801203a0  mov     rax, [rax+10h]
0x1801203a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801203a9  xor     edi, edi
0x1801203ab  mov     rcx, rsi; lpCriticalSection
0x1801203ae  call    cs:__imp_LeaveCriticalSection
0x1801203b5  nop     dword ptr [rax+rax+00h]
0x1801203ba  mov     eax, edi
0x1801203bc  add     rsp, 58h
0x1801203c0  pop     rdi
0x1801203c1  pop     rsi
0x1801203c2  pop     rbx
0x1801203c3  pop     rbp
0x1801203c4  retn
```
