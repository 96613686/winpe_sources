# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180003440`
- end: `0x180003568`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `296`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(unsigned int, int, struct IHttpContext *, struct IHttpEventProvider *, struct IHttpCompletionInfo *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002990`
- `0x1800029f0`

## callees

- `0x1800023cc`
- `0x180003440`
- `0x18000b010`

## pseudocode

```c
__int64 RequestDoWork(__int64 a1, __int64 a2, struct IHttpContext *a3, ...)
{
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rax
  int v7; // edi
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF
  struct INativeSectionException *v10; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, struct INativeSectionException *);
  v4 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  v10 = 0;
  v6 = *(_QWORD *)a3;
  v9 = 0;
  if ( !(*(__int64 (__fastcall **)(struct IHttpContext *))(v6 + 232))(a3) )
  {
    v7 = HandleRootRqBeginRequest(a3, (struct INativeSectionException **)va);
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 80LL))(v5);
      if ( v10 )
      {
        (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v10)(
          v10,
          &IID_IAppHostConfigException,
          &v9);
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v5 + 24LL))(
          v5,
          500,
          "Internal Server Error",
          19,
          v7,
          v9,
          0);
      }
      else
      {
        (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
          v5,
          500,
          "Internal Server Error",
          0,
          v7,
          0,
          0);
      }
      v4 = 2;
    }
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v4;
}

```

## disassembly

```asm
0x180003440  mov     [rsp+arg_0], rbx
0x180003445  mov     [rsp+arg_8], rsi
0x18000344a  mov     [rsp+arg_18], r9
0x18000344f  push    rdi
0x180003450  sub     rsp, 40h
0x180003454  mov     rax, [r8]
0x180003457  mov     rcx, r8
0x18000345a  mov     rdi, r8
0x18000345d  xor     esi, esi
0x18000345f  mov     rax, [rax+20h]
0x180003463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003468  mov     rbx, rax
0x18000346b  mov     [rsp+48h+arg_18], rsi
0x180003470  mov     rax, [rdi]
0x180003473  mov     rcx, rdi
0x180003476  mov     [rsp+48h+arg_10], rsi
0x18000347b  mov     rax, [rax+0E8h]
0x180003482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003487  test    rax, rax
0x18000348a  jnz     loc_180003521
0x180003490  lea     rdx, [rsp+48h+arg_18]; struct INativeSectionException **
0x180003495  mov     rcx, rdi; struct IHttpContext *
0x180003498  call    ?HandleRootRqBeginRequest@@YAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; HandleRootRqBeginRequest(IHttpContext *,INativeSectionException * *)
0x18000349d  mov     edi, eax
0x18000349f  test    eax, eax
0x1800034a1  jns     short loc_180003521
0x1800034a3  mov     rax, [rbx]
0x1800034a6  mov     rcx, rbx
0x1800034a9  mov     rax, [rax+50h]
0x1800034ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b2  mov     rcx, [rsp+48h+arg_18]
0x1800034b7  test    rcx, rcx
0x1800034ba  jz      short loc_1800034F1
0x1800034bc  mov     rax, [rcx]
0x1800034bf  lea     r8, [rsp+48h+arg_10]
0x1800034c4  lea     rdx, IID_IAppHostConfigException
0x1800034cb  mov     rax, [rax]
0x1800034ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d3  mov     rax, [rbx]
0x1800034d6  lea     r9d, [rsi+13h]
0x1800034da  mov     [rsp+48h+var_18], esi
0x1800034de  mov     r10, [rax+18h]
0x1800034e2  mov     rax, [rsp+48h+arg_10]
0x1800034e7  mov     [rsp+48h+var_20], rax
0x1800034ec  mov     rax, r10
0x1800034ef  jmp     short loc_180003504
0x1800034f1  mov     rax, [rbx]
0x1800034f4  xor     r9d, r9d
0x1800034f7  mov     [rsp+48h+var_18], esi
0x1800034fb  mov     [rsp+48h+var_20], rsi
0x180003500  mov     rax, [rax+18h]
0x180003504  lea     r8, aInternalServer; "Internal Server Error"
0x18000350b  mov     [rsp+48h+var_28], edi
0x18000350f  mov     edx, 1F4h
0x180003514  mov     rcx, rbx
0x180003517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351c  mov     esi, 2
0x180003521  mov     rcx, [rsp+48h+arg_18]
0x180003526  test    rcx, rcx
0x180003529  jz      short loc_180003540
0x18000352b  mov     rax, [rcx]
0x18000352e  mov     rax, [rax+10h]
0x180003532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003537  mov     [rsp+48h+arg_18], 0
0x180003540  mov     rcx, [rsp+48h+arg_10]
0x180003545  test    rcx, rcx
0x180003548  jz      short loc_180003556
0x18000354a  mov     rdx, [rcx]
0x18000354d  mov     rax, [rdx+10h]
0x180003551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003556  mov     rbx, [rsp+48h+arg_0]
0x18000355b  mov     eax, esi
0x18000355d  mov     rsi, [rsp+48h+arg_8]
0x180003562  add     rsp, 40h
0x180003566  pop     rdi
0x180003567  retn
```
