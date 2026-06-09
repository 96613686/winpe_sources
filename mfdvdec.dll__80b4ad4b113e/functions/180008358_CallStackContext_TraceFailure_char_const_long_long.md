# CallStackContext::TraceFailure(char const *,long,long)

- ea: `0x180008358`
- end: `0x180008458`
- name: `?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z`
- size: `256`
- prototype: `void __fastcall(CallStackContext *__hidden this, const char *, int, int)`
- caller_count: `19`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002370`
- `0x180002540`
- `0x180002810`
- `0x180002ac0`
- `0x180003678`
- `0x1800039e0`
- `0x180003e30`
- `0x180004060`
- `0x1800041dc`
- `0x18000440c`
- `0x180004818`
- `0x180004c54`
- `0x180004fc0`
- `0x180005340`
- `0x1800057a0`
- `0x180005db0`
- `0x180005fbc`
- `0x180006b70`
- `0x180006fd4`

## callees

- `0x180001580`
- `0x180008358`
- `0x1800084ec`
- `0x18001e010`

## pseudocode

```c
void __fastcall CallStackContext::TraceFailure(CallStackContext *this, const char *a2, unsigned int a3, __int64 a4)
{
  int v4; // edi
  const int *v8; // rcx
  __int64 v9; // rax
  bool v10; // cc
  unsigned int v11; // [rsp+30h] [rbp-49h] BYREF
  int v12; // [rsp+38h] [rbp-41h] BYREF
  CallStackTracing *v13; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-29h] BYREF
  CallStackTracing **v15; // [rsp+60h] [rbp-19h]
  __int64 v16; // [rsp+68h] [rbp-11h]
  int *v17; // [rsp+70h] [rbp-9h]
  __int64 v18; // [rsp+78h] [rbp-1h]
  int *v19; // [rsp+80h] [rbp+7h]
  __int64 v20; // [rsp+88h] [rbp+Fh]
  const int *v21; // [rsp+90h] [rbp+17h]
  int v22; // [rsp+98h] [rbp+1Fh]
  int v23; // [rsp+9Ch] [rbp+23h]

  v4 = a4;
  if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
  {
    v12 = a4;
    v11 = a3;
    v16 = 8;
    v8 = (const int *)a2;
    v18 = 4;
    if ( !a2 )
      v8 = &qword_1800202C8;
    v20 = 4;
    v13 = CallStackTracing::s_wpInstance;
    v15 = &v13;
    v17 = (int *)&v11;
    v19 = &v12;
    v9 = -1;
    do
      ++v9;
    while ( *((_BYTE *)v8 + v9) );
    v21 = v8;
    v22 = v9 + 1;
    v23 = 0;
    McGenEventWrite_EventWriteTransfer((__int64)v8, (__int64)a2, 0, a4, &v14);
  }
  v10 = ++*((_DWORD *)this + 506) <= 0xAu;
  *((_DWORD *)this + 499) = v4;
  if ( v10 )
    (*(void (__fastcall **)(CallStackTracing *, CallStackContext *, const char *, _QWORD))(*(_QWORD *)CallStackTracing::s_wpInstance
                                                                                         + 16LL))(
      CallStackTracing::s_wpInstance,
      this,
      a2,
      a3);
}

```

## disassembly

```asm
0x180008358  push    rbp
0x18000835a  push    rbx
0x18000835b  push    rsi
0x18000835c  push    rdi
0x18000835d  push    r14
0x18000835f  lea     rbp, [rsp-37h]
0x180008364  sub     rsp, 0B0h
0x18000836b  mov     rax, cs:__security_cookie
0x180008372  xor     rax, rsp
0x180008375  mov     [rbp+57h+var_30], rax
0x180008379  test    cs:Microsoft_Windows_MediaFoundation_PlatformEnableBits, 2
0x180008380  mov     edi, r9d
0x180008383  mov     r14d, r8d
0x180008386  mov     rsi, rdx
0x180008389  mov     rbx, rcx
0x18000838c  jz      short loc_18000840D
0x18000838e  xor     r8d, r8d; int
0x180008391  mov     [rbp+57h+var_98], r9d
0x180008395  test    rdx, rdx
0x180008398  mov     [rbp+57h+var_A0], r14d
0x18000839c  lea     rax, qword_1800202C8
0x1800083a3  mov     [rbp+57h+var_68], 8
0x1800083ab  mov     rcx, rdx
0x1800083ae  mov     [rbp+57h+var_58], 4
0x1800083b6  cmovz   rcx, rax; int
0x1800083ba  mov     [rbp+57h+var_48], 4
0x1800083c2  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800083c9  mov     [rbp+57h+var_90], rax
0x1800083cd  lea     rax, [rbp+57h+var_90]
0x1800083d1  mov     [rbp+57h+var_70], rax
0x1800083d5  lea     rax, [rbp+57h+var_A0]
0x1800083d9  mov     [rbp+57h+var_60], rax
0x1800083dd  lea     rax, [rbp+57h+var_98]
0x1800083e1  mov     [rbp+57h+var_50], rax
0x1800083e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800083e9  inc     rax
0x1800083ec  cmp     [rcx+rax], r8b
0x1800083f0  jnz     short loc_1800083E9
0x1800083f2  inc     eax
0x1800083f4  mov     [rbp+57h+var_40], rcx
0x1800083f8  mov     [rbp+57h+var_38], eax
0x1800083fb  lea     rax, [rbp+57h+var_80]
0x1800083ff  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x180008404  mov     [rbp+57h+var_34], r8d
0x180008408  call    McGenEventWrite_EventWriteTransfer
0x18000840d  inc     dword ptr [rbx+7E8h]
0x180008413  cmp     dword ptr [rbx+7E8h], 0Ah
0x18000841a  mov     [rbx+7CCh], edi
0x180008420  ja      short loc_18000843E
0x180008422  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180008429  mov     r9d, r14d
0x18000842c  mov     r8, rsi
0x18000842f  mov     rdx, rbx
0x180008432  mov     rax, [rcx]
0x180008435  mov     rax, [rax+10h]
0x180008439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843e  mov     rcx, [rbp+57h+var_30]
0x180008442  xor     rcx, rsp; StackCookie
0x180008445  call    __security_check_cookie
0x18000844a  add     rsp, 0B0h
0x180008451  pop     r14
0x180008453  pop     rdi
0x180008454  pop     rsi
0x180008455  pop     rbx
0x180008456  pop     rbp
0x180008457  retn
```
