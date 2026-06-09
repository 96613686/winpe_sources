# wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180080840`
- end: `0x1800808b3`
- name: `??R?$__func@V_lambda_42d7dced1872ed24a4c1197da8e68253_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180017c80`
- `0x180080840`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180080872`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180080872`

## string_xrefs

- `0x18008088e`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\persistentlocationhelper.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::operator()(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3,
        unsigned __int64 **a4)
{
  unsigned __int64 *v4; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // rcx
  unsigned int PersistedRegistryLocationW; // eax
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v13; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a4;
  v6 = *(_QWORD **)(a1 + 8);
  v7 = *a3;
  v8 = *(_QWORD **)(a1 + 16);
  v13 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(*v8, *v6, *a2, v7);
  v10 = 0;
  if ( PersistedRegistryLocationW != 234 )
    v10 = (const char *)PersistedRegistryLocationW;
  if ( (_DWORD)v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1F,
             (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
             v10,
             (unsigned int)&v13);
  *v4 = (unsigned __int64)v13 >> 1;
  return 0;
}

```

## disassembly

```asm
0x180080840  push    rbx
0x180080842  sub     rsp, 30h
0x180080846  mov     rbx, [r9]
0x180080849  mov     rax, rdx
0x18008084c  mov     rdx, [rcx+8]
0x180080850  mov     r9d, [r8]
0x180080853  lea     r8, [rsp+38h+arg_0]
0x180080858  mov     rcx, [rcx+10h]
0x18008085c  mov     [rsp+38h+arg_0], 0
0x180080864  mov     rdx, [rdx]
0x180080867  mov     qword ptr [rsp+38h+var_18], r8; unsigned int
0x18008086c  mov     rcx, [rcx]
0x18008086f  mov     r8, [rax]
0x180080872  call    cs:__imp_GetPersistedRegistryLocationW
0x180080878  xor     r9d, r9d
0x18008087b  cmp     eax, 0EAh
0x180080880  cmovnz  r9d, eax; char *
0x180080884  test    r9d, r9d
0x180080887  jz      short loc_1800808A1
0x180080889  mov     rcx, [rsp+38h]; this
0x18008088e  lea     r8, aShellcommondes; "shellcommondesktopbase\\base\\embedded"...
0x180080895  mov     edx, 1Fh; void *
0x18008089a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008089f  jmp     short loc_1800808AD
0x1800808a1  mov     eax, [rsp+38h+arg_0]
0x1800808a5  shr     rax, 1
0x1800808a8  mov     [rbx], rax
0x1800808ab  xor     eax, eax
0x1800808ad  add     rsp, 30h
0x1800808b1  pop     rbx
0x1800808b2  retn
```
