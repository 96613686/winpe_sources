# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000471c`
- end: `0x180004962`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(int, int, struct IHttpContext *, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003c90`
- `0x180003d00`

## callees

- `0x1800012c0`
- `0x18000471c`
- `0x180005394`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(int a1, int a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  __int64 v7; // rsi
  __int64 v8; // r15
  __int64 (__fastcall ***v9)(_QWORD, void *); // rax
  CUSTOM_ERROR_HANDLER *v10; // rbx
  void (__fastcall *v11)(__int64, int *, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  CUSTOM_ERROR_HANDLER *v12; // rax
  __int64 v13; // rax
  int v14; // r8d
  int v16; // [rsp+90h] [rbp+8h] BYREF
  int v17; // [rsp+98h] [rbp+10h] BYREF

  v17 = a2;
  v16 = a1;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  v8 = a5;
  v9 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
  v10 = (CUSTOM_ERROR_HANDLER *)(**v9)(v9, s_pCustomErrorModuleContext);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    (**(void (__fastcall ***)(__int64))v8)(v8);
    v14 = 1;
    return CUSTOM_ERROR_HANDLER::DoWork(v10, a3, v14);
  }
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4) )
  {
    if ( !v10 )
    {
      v11 = *(void (__fastcall **)(__int64, int *, int *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v7 + 184LL);
      LOWORD(v17) = 0;
      LOWORD(v16) = 0;
      v11(v7, &v17, &v16, 0, 0, 0, 0, 0, 0, 0);
      if ( (unsigned __int16)v17 < 0x190u
        || ((*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 112LL))(a3) & 8) != 0 )
      {
        TraceNotSendCustomError(a3, 1);
        return 0;
      }
      v12 = (CUSTOM_ERROR_HANDLER *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(
                                      a3,
                                      40);
      v10 = v12;
      if ( !v12 )
      {
        (**(void (__fastcall ***)(__int64, __int64))a4)(a4, 2147942408LL);
        return 0;
      }
      *((_QWORD *)v12 + 1) = 0;
      *(_QWORD *)v12 = &CUSTOM_ERROR_HANDLER::`vftable';
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 3) = 1;
      v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
      if ( (*(int (__fastcall **)(__int64, CUSTOM_ERROR_HANDLER *, void *))(*(_QWORD *)v13 + 8LL))(
             v13,
             v10,
             s_pCustomErrorModuleContext) < 0 )
      {
        (**(void (__fastcall ***)(CUSTOM_ERROR_HANDLER *))v10)(v10);
        return 0;
      }
      if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4) & 2) != 0
        || *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) + 536) )
      {
        *((_DWORD *)v10 + 6) = 0;
      }
      v14 = 0;
      return CUSTOM_ERROR_HANDLER::DoWork(v10, a3, v14);
    }
  }
  else if ( !v10 )
  {
    return 0;
  }
  if ( !*((_DWORD *)v10 + 7) )
    return 0;
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7) + 536) = 0;
  return 2;
}

```

## disassembly

```asm
0x18000471c  mov     [rsp+arg_10], rbx
0x180004721  mov     [rsp+arg_8], edx
0x180004725  mov     [rsp+arg_0], ecx
0x180004729  push    rbp
0x18000472a  push    rsi
0x18000472b  push    rdi
0x18000472c  push    r14
0x18000472e  push    r15
0x180004730  sub     rsp, 60h
0x180004734  mov     rax, [r8]
0x180004737  mov     rcx, r8
0x18000473a  mov     r14, r9
0x18000473d  mov     rdi, r8
0x180004740  mov     rax, [rax+20h]
0x180004744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004749  mov     rcx, [rdi]
0x18000474c  mov     rsi, rax
0x18000474f  mov     r15, [rsp+88h+arg_20]
0x180004757  xor     ebp, ebp
0x180004759  mov     rax, [rcx+38h]
0x18000475d  mov     rcx, rdi
0x180004760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004765  mov     rdx, cs:?s_pCustomErrorModuleContext@@3PEAXEA; void * s_pCustomErrorModuleContext
0x18000476c  mov     r8, rax
0x18000476f  mov     rcx, [rax]
0x180004772  mov     rax, [rcx]
0x180004775  mov     rcx, r8
0x180004778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000477d  mov     rbx, rax
0x180004780  test    r15, r15
0x180004783  jnz     loc_180004920
0x180004789  mov     rcx, [r14]
0x18000478c  mov     rax, [rcx+8]
0x180004790  mov     rcx, r14
0x180004793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004798  test    eax, eax
0x18000479a  jz      loc_1800048F9
0x1800047a0  test    rbx, rbx
0x1800047a3  jnz     loc_1800048FE
0x1800047a9  mov     rax, [rsi]
0x1800047ac  lea     r8, [rsp+88h+arg_0]
0x1800047b4  mov     [rsp+88h+var_40], rbp
0x1800047b9  lea     rdx, [rsp+88h+arg_8]
0x1800047c1  mov     [rsp+88h+var_48], rbp
0x1800047c6  xor     r9d, r9d
0x1800047c9  mov     [rsp+88h+var_50], rbp
0x1800047ce  mov     rcx, rsi
0x1800047d1  mov     rax, [rax+0B8h]
0x1800047d8  mov     [rsp+88h+var_58], rbp
0x1800047dd  mov     [rsp+88h+var_60], rbp
0x1800047e2  mov     word ptr [rsp+88h+arg_8], bp
0x1800047ea  mov     word ptr [rsp+88h+arg_0], bp
0x1800047f2  mov     [rsp+88h+var_68], rbp
0x1800047f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047fc  mov     eax, 190h
0x180004801  cmp     word ptr [rsp+88h+arg_8], ax
0x180004809  jb      loc_1800048E8
0x18000480f  mov     rax, [rdi]
0x180004812  mov     rcx, rdi
0x180004815  mov     rax, [rax+70h]
0x180004819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000481e  test    al, 8
0x180004820  jnz     loc_1800048E8
0x180004826  mov     rax, [rdi]
0x180004829  lea     edx, [rbp+28h]
0x18000482c  mov     rcx, rdi
0x18000482f  mov     rax, [rax+90h]
0x180004836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000483b  mov     rbx, rax
0x18000483e  test    rax, rax
0x180004841  jz      loc_1800048D3
0x180004847  lea     rax, ??_7CUSTOM_ERROR_HANDLER@@6B@; const CUSTOM_ERROR_HANDLER::`vftable'
0x18000484e  mov     [rbx+8], rbp
0x180004852  mov     [rbx], rax
0x180004855  mov     [rbx+10h], rbp
0x180004859  mov     qword ptr [rbx+18h], 1
0x180004861  mov     rcx, [rdi]
0x180004864  mov     rax, [rcx+38h]
0x180004868  mov     rcx, rdi
0x18000486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004870  mov     r8, cs:?s_pCustomErrorModuleContext@@3PEAXEA; void * s_pCustomErrorModuleContext
0x180004877  mov     r9, rax
0x18000487a  mov     rdx, rbx
0x18000487d  mov     rcx, [rax]
0x180004880  mov     rax, [rcx+8]
0x180004884  mov     rcx, r9
0x180004887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488c  test    eax, eax
0x18000488e  jns     short loc_1800048A0
0x180004890  mov     rax, [rbx]
0x180004893  mov     rcx, rbx
0x180004896  mov     rax, [rax]
0x180004899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489e  jmp     short loc_1800048F5
0x1800048a0  mov     rax, [r14]
0x1800048a3  mov     rcx, r14
0x1800048a6  mov     rax, [rax+10h]
0x1800048aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048af  test    al, 2
0x1800048b1  jnz     short loc_1800048CB
0x1800048b3  mov     rax, [rsi]
0x1800048b6  mov     rcx, rsi
0x1800048b9  mov     rax, [rax+8]
0x1800048bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c2  cmp     [rax+218h], bp
0x1800048c9  jz      short loc_1800048CE
0x1800048cb  mov     [rbx+18h], ebp
0x1800048ce  xor     r8d, r8d
0x1800048d1  jmp     short loc_180004943
0x1800048d3  mov     rax, [r14]
0x1800048d6  mov     edx, 80070008h
0x1800048db  mov     rcx, r14
0x1800048de  mov     rax, [rax]
0x1800048e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e6  jmp     short loc_1800048F5
0x1800048e8  mov     edx, 1
0x1800048ed  mov     rcx, rdi
0x1800048f0  call    ?TraceNotSendCustomError@@YAXPEAVIHttpContext@@W4enumReason@GENERAL_NOT_SEND_CUSTOM_ERROR@IISGeneralEvents@@@Z; TraceNotSendCustomError(IHttpContext *,IISGeneralEvents::GENERAL_NOT_SEND_CUSTOM_ERROR::enumReason)
0x1800048f5  xor     eax, eax
0x1800048f7  jmp     short loc_18000494E
0x1800048f9  test    rbx, rbx
0x1800048fc  jz      short loc_1800048F5
0x1800048fe  cmp     [rbx+1Ch], ebp
0x180004901  jz      short loc_1800048F5
0x180004903  mov     rax, [rsi]
0x180004906  mov     rcx, rsi
0x180004909  mov     rax, [rax+8]
0x18000490d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004912  mov     [rax+218h], bp
0x180004919  mov     eax, 2
0x18000491e  jmp     short loc_18000494E
0x180004920  mov     rdx, [r15]
0x180004923  mov     rcx, r15
0x180004926  mov     rax, [rdx+8]
0x18000492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492f  mov     rdx, [r15]
0x180004932  mov     rcx, r15
0x180004935  mov     rax, [rdx]
0x180004938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000493d  mov     r8d, 1
0x180004943  mov     rdx, rdi
0x180004946  mov     rcx, rbx
0x180004949  call    ?DoWork@CUSTOM_ERROR_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@HKJ@Z; CUSTOM_ERROR_HANDLER::DoWork(IHttpContext *,int,ulong,long)
0x18000494e  mov     rbx, [rsp+88h+arg_10]
0x180004956  add     rsp, 60h
0x18000495a  pop     r15
0x18000495c  pop     r14
0x18000495e  pop     rdi
0x18000495f  pop     rsi
0x180004960  pop     rbp
0x180004961  retn
```
