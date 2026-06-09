# CImplMediaEvent::CEventStore::Deliver(long,__int64,__int64)

- ea: `0x1800206c8`
- end: `0x1800208d2`
- name: `?Deliver@CEventStore@CImplMediaEvent@@QEAAJJ_J0@Z`
- size: `522`
- prototype: `int(CImplMediaEvent::CEventStore *__hidden this, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800706c8`
- `0x1800711ec`
- `0x180071720`
- `0x1800777d8`

## callees

- `0x18001a050`
- `0x1800206c8`
- `0x1800274d0`
- `0x180038458`
- `0x18005d5f8`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002072c`
- `KERNEL32!SetEvent` at `0x180020790`
- `KERNEL32!SetEvent` at `0x18002072c`
- `KERNEL32!SetEvent` at `0x180020790`
- `KERNEL32!LeaveCriticalSection` at `0x1800208b6`
- `KERNEL32!LeaveCriticalSection` at `0x1800208b6`
- `KERNEL32!EnterCriticalSection` at `0x1800206e4`
- `KERNEL32!EnterCriticalSection` at `0x1800206e4`
- `USER32!PostMessageW` at `0x18002074f`
- `USER32!PostMessageW` at `0x18002074f`
- `ole32!CoTaskMemFree` at `0x18002087c`
- `ole32!CoTaskMemFree` at `0x18002088e`
- `ole32!CoTaskMemFree` at `0x18002087c`
- `ole32!CoTaskMemFree` at `0x18002088e`

## pseudocode

```c
__int64 __fastcall CImplMediaEvent::CEventStore::Deliver(
        CImplMediaEvent::CEventStore *this,
        int a2,
        _QWORD *a3,
        __int64 a4)
{
  int *v8; // rax
  int *v9; // r15
  unsigned int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  _QWORD *v17; // rbx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  char *v27; // rdi
  char *v28; // rdi
  char *v29; // rdi
  _QWORD *v31; // [rsp+20h] [rbp-48h] BYREF
  __int64 v32; // [rsp+70h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( (*((_BYTE *)this + 32) & 1) != 0 )
  {
    if ( a2 == 1 )
      SetEvent(*((HANDLE *)this + 3));
    v32 = a4;
    v31 = a3;
    if ( a2 > 26 )
    {
      v21 = a2 - 27;
      if ( !v21 )
        goto LABEL_42;
      v22 = v21 - 1;
      if ( !v22 )
      {
LABEL_24:
        v18 = a3;
        goto LABEL_40;
      }
      v23 = v22 - 3;
      if ( !v23 )
        goto LABEL_42;
      v24 = v23 - 6;
      if ( v24 )
      {
        v25 = v24 - 28;
        if ( !v25 )
        {
LABEL_19:
          FreeBSTR(&v31);
LABEL_20:
          FreeBSTR(&v32);
          goto LABEL_45;
        }
        v26 = v25 - 4;
        if ( !v26 )
          goto LABEL_20;
        if ( v26 != 525 || !a4 )
          goto LABEL_45;
        v27 = (char *)a3 - 9;
        if ( v27 )
        {
          v28 = v27 - 14;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              if ( v29 != (char *)2 )
                goto LABEL_45;
            }
          }
        }
        else
        {
          CoTaskMemFree(*(LPVOID *)(a4 + 8));
        }
        v18 = (void *)a4;
LABEL_40:
        CoTaskMemFree(v18);
        goto LABEL_45;
      }
    }
    else
    {
      if ( a2 == 26 )
        goto LABEL_42;
      v11 = a2 - 1;
      if ( !v11 )
        goto LABEL_25;
      v12 = v11 - 4;
      if ( !v12 )
      {
LABEL_42:
        if ( !a3 )
          goto LABEL_45;
        v19 = *a3;
        v20 = a3;
        goto LABEL_44;
      }
      v13 = v12 - 13;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 2;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 != 2 )
              {
LABEL_45:
                v10 = 0;
                goto LABEL_46;
              }
              goto LABEL_19;
            }
            if ( (_DWORD)a4 )
            {
              v17 = a3;
              do
              {
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 16LL))(*v17);
                ++v17;
                LODWORD(a4) = a4 - 1;
              }
              while ( (_DWORD)a4 );
              goto LABEL_24;
            }
          }
          goto LABEL_42;
        }
      }
    }
LABEL_25:
    if ( !a4 )
      goto LABEL_45;
    v19 = *(_QWORD *)a4;
    v20 = (_QWORD *)a4;
LABEL_44:
    (*(void (__fastcall **)(_QWORD *))(v19 + 16))(v20);
    goto LABEL_45;
  }
  v8 = (int *)operator new(0x18u);
  v9 = v8;
  if ( v8 )
  {
    *v8 = a2;
    *((_QWORD *)v8 + 1) = a3;
    *((_QWORD *)v8 + 2) = a4;
    if ( CBaseList::AddTailI((CImplMediaEvent::CEventStore *)((char *)this + 40), v8) )
    {
      SetEvent(*((HANDLE *)this + 3));
      if ( *(_QWORD *)this )
        PostMessageW(*(HWND *)this, *((_DWORD *)this + 2), 0, *((_QWORD *)this + 2));
      goto LABEL_45;
    }
  }
  else
  {
    v9 = 0;
  }
  operator delete(v9);
  CImplMediaEvent::RealFreeEventParams(a2, (__int64)a3, a4);
  v10 = -2147024882;
LABEL_46:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  return v10;
}

```

## disassembly

```asm
0x1800206c8  push    rbx
0x1800206ca  push    rbp
0x1800206cb  push    rsi
0x1800206cc  push    rdi
0x1800206cd  push    r14
0x1800206cf  push    r15
0x1800206d1  sub     rsp, 38h
0x1800206d5  mov     r14, rcx
0x1800206d8  mov     rsi, r9
0x1800206db  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800206df  mov     rdi, r8
0x1800206e2  mov     ebx, edx
0x1800206e4  call    cs:__imp_EnterCriticalSection
0x1800206eb  nop     dword ptr [rax+rax+00h]
0x1800206f0  test    byte ptr [r14+20h], 1
0x1800206f5  jnz     loc_180020787
0x1800206fb  mov     ecx, 18h; Size
0x180020700  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020705  mov     r15, rax
0x180020708  test    rax, rax
0x18002070b  jz      short loc_180020760
0x18002070d  lea     rcx, [r14+28h]; this
0x180020711  mov     [rax], ebx
0x180020713  mov     rdx, rax; void *
0x180020716  mov     [rax+8], rdi
0x18002071a  mov     [rax+10h], rsi
0x18002071e  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x180020723  test    rax, rax
0x180020726  jz      short loc_180020763
0x180020728  mov     rcx, [r14+18h]; hEvent
0x18002072c  call    cs:__imp_SetEvent
0x180020733  nop     dword ptr [rax+rax+00h]
0x180020738  mov     rcx, [r14]; hWnd
0x18002073b  test    rcx, rcx
0x18002073e  jz      loc_1800208B0
0x180020744  mov     r9, [r14+10h]; lParam
0x180020748  xor     r8d, r8d; wParam
0x18002074b  mov     edx, [r14+8]; Msg
0x18002074f  call    cs:__imp_PostMessageW
0x180020756  nop     dword ptr [rax+rax+00h]
0x18002075b  jmp     loc_1800208B0
0x180020760  xor     r15d, r15d
0x180020763  mov     edx, 18h
0x180020768  mov     rcx, r15; Block
0x18002076b  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180020770  mov     r8, rsi; __int64
0x180020773  mov     rdx, rdi; __int64
0x180020776  mov     ecx, ebx; int
0x180020778  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x18002077d  mov     ebx, 8007000Eh
0x180020782  jmp     loc_1800208B2
0x180020787  cmp     ebx, 1
0x18002078a  jnz     short loc_18002079C
0x18002078c  mov     rcx, [r14+18h]; hEvent
0x180020790  call    cs:__imp_SetEvent
0x180020797  nop     dword ptr [rax+rax+00h]
0x18002079c  mov     [rsp+68h+arg_0], rsi
0x1800207a1  mov     [rsp+68h+var_48], rdi
0x1800207a6  cmp     ebx, 1Ah
0x1800207a9  jg      loc_180020836
0x1800207af  jz      loc_18002089C
0x1800207b5  sub     ebx, 1
0x1800207b8  jz      short loc_180020825
0x1800207ba  sub     ebx, 4
0x1800207bd  jz      loc_18002089C
0x1800207c3  sub     ebx, 0Dh
0x1800207c6  jz      short loc_180020825
0x1800207c8  sub     ebx, 1
0x1800207cb  jz      short loc_180020825
0x1800207cd  sub     ebx, 2
0x1800207d0  jz      loc_18002089C
0x1800207d6  sub     ebx, 1
0x1800207d9  jz      short loc_1800207FD
0x1800207db  cmp     ebx, 2
0x1800207de  jnz     loc_1800208B0
0x1800207e4  lea     rcx, [rsp+68h+var_48]
0x1800207e9  call    FreeBSTR
0x1800207ee  lea     rcx, [rsp+68h+arg_0]
0x1800207f3  call    FreeBSTR
0x1800207f8  jmp     loc_1800208B0
0x1800207fd  test    esi, esi
0x1800207ff  jz      loc_18002089C
0x180020805  mov     rbx, rdi
0x180020808  mov     rcx, [rbx]
0x18002080b  mov     rax, [rcx]
0x18002080e  mov     rax, [rax+10h]
0x180020812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020817  lea     rbx, [rbx+8]
0x18002081b  add     esi, 0FFFFFFFFh
0x18002081e  jnz     short loc_180020808
0x180020820  mov     rcx, rdi
0x180020823  jmp     short loc_18002087C
0x180020825  test    rsi, rsi
0x180020828  jz      loc_1800208B0
0x18002082e  mov     rax, [rsi]
0x180020831  mov     rcx, rsi
0x180020834  jmp     short loc_1800208A7
0x180020836  sub     ebx, 1Bh
0x180020839  jz      short loc_18002089C
0x18002083b  sub     ebx, 1
0x18002083e  jz      short loc_180020820
0x180020840  sub     ebx, 3
0x180020843  jz      short loc_18002089C
0x180020845  sub     ebx, 6
0x180020848  jz      short loc_180020825
0x18002084a  sub     ebx, 1Ch
0x18002084d  jz      short loc_1800207E4
0x18002084f  sub     ebx, 4
0x180020852  jz      short loc_1800207EE
0x180020854  cmp     ebx, 20Dh
0x18002085a  jnz     short loc_1800208B0
0x18002085c  test    rsi, rsi
0x18002085f  jz      short loc_1800208B0
0x180020861  sub     rdi, 9
0x180020865  jz      short loc_18002088A
0x180020867  sub     rdi, 0Eh
0x18002086b  jz      short loc_180020879
0x18002086d  sub     rdi, 1
0x180020871  jz      short loc_180020879
0x180020873  cmp     rdi, 2
0x180020877  jnz     short loc_1800208B0
0x180020879  mov     rcx, rsi; pv
0x18002087c  call    cs:__imp_CoTaskMemFree
0x180020883  nop     dword ptr [rax+rax+00h]
0x180020888  jmp     short loc_1800208B0
0x18002088a  mov     rcx, [rsi+8]; pv
0x18002088e  call    cs:__imp_CoTaskMemFree
0x180020895  nop     dword ptr [rax+rax+00h]
0x18002089a  jmp     short loc_180020879
0x18002089c  test    rdi, rdi
0x18002089f  jz      short loc_1800208B0
0x1800208a1  mov     rax, [rdi]
0x1800208a4  mov     rcx, rdi
0x1800208a7  mov     rax, [rax+10h]
0x1800208ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208b0  xor     ebx, ebx
0x1800208b2  lea     rcx, [r14+50h]; lpCriticalSection
0x1800208b6  call    cs:__imp_LeaveCriticalSection
0x1800208bd  nop     dword ptr [rax+rax+00h]
0x1800208c2  mov     eax, ebx
0x1800208c4  add     rsp, 38h
0x1800208c8  pop     r15
0x1800208ca  pop     r14
0x1800208cc  pop     rdi
0x1800208cd  pop     rsi
0x1800208ce  pop     rbp
0x1800208cf  pop     rbx
0x1800208d0  retn
```
