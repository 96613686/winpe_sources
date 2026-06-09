# CheckForHeaderRestrictions(REQUEST_FILTER_CONFIG *,IHttpContext *,int *)

- ea: `0x180006f30`
- end: `0x180007043`
- name: `?CheckForHeaderRestrictions@@YAJPEAVREQUEST_FILTER_CONFIG@@PEAVIHttpContext@@PEAH@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct REQUEST_FILTER_CONFIG *, struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800010c0`

## callees

- `0x180006f30`
- `0x180008010`

## import_xrefs

- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006fa4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006fe4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006fa4`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006fe4`
- `iisutil!PuDbgPrint` at `0x18000701a`
- `iisutil!PuDbgPrint` at `0x18000701a`

## string_xrefs

- `0x180006ffc`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\requestfiltering.cxx`

## pseudocode

```c
__int64 __fastcall CheckForHeaderRestrictions(struct REQUEST_FILTER_CONFIG *a1, struct IHttpContext *a2, int *a3)
{
  unsigned int v3; // r12d
  __int64 i; // rsi
  STRA *v8; // rbp
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, char *, unsigned __int16 *); // rbx
  char *Str; // rax
  unsigned int v12; // ebx
  const char *v13; // rax
  unsigned __int16 v15; // [rsp+90h] [rbp+8h] BYREF

  v3 = *((_DWORD *)a1 + 142);
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    {
      v15 = 0;
      if ( (unsigned int)i < *((_DWORD *)a1 + 142) )
        v8 = *(STRA **)(*((_QWORD *)a1 + 70) + 8 * i);
      else
        v8 = 0;
      v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v10 = *(__int64 (__fastcall **)(__int64, char *, unsigned __int16 *))(*(_QWORD *)v9 + 24LL);
      Str = STRA::QueryStr(v8);
      if ( v10(v9, Str, &v15) )
      {
        v12 = *((_DWORD *)v8 + 14);
        if ( v15 > v12 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v13 = STRA::QueryStr(v8);
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\requestfiltering.cxx",
              1552,
              "CheckForHeaderRestrictions",
              "The value of header '%s' exceeds %d characters.\r\n",
              v13,
              v12);
          }
          *a3 = 1;
          return 0;
        }
      }
    }
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180006f30  push    rbx
0x180006f32  push    rbp
0x180006f33  push    rsi
0x180006f34  push    rdi
0x180006f35  push    r12
0x180006f37  push    r13
0x180006f39  push    r14
0x180006f3b  push    r15
0x180006f3d  sub     rsp, 48h
0x180006f41  mov     r12d, [rcx+238h]
0x180006f48  mov     r15, r8
0x180006f4b  mov     r13, rdx
0x180006f4e  mov     r14, rcx
0x180006f51  test    r12d, r12d
0x180006f54  jz      loc_180007029
0x180006f5a  xor     esi, esi
0x180006f5c  cmp     esi, r12d
0x180006f5f  jnb     loc_180007029
0x180006f65  xor     eax, eax
0x180006f67  mov     [rsp+88h+arg_0], ax
0x180006f6f  cmp     esi, [r14+238h]
0x180006f76  jb      short loc_180006F7C
0x180006f78  xor     ebp, ebp
0x180006f7a  jmp     short loc_180006F87
0x180006f7c  mov     rax, [r14+230h]
0x180006f83  mov     rbp, [rax+rsi*8]
0x180006f87  mov     rax, [r13+0]
0x180006f8b  mov     rcx, r13
0x180006f8e  mov     rax, [rax+18h]
0x180006f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f97  mov     rdi, rax
0x180006f9a  mov     rcx, [rax]
0x180006f9d  mov     rbx, [rcx+18h]
0x180006fa1  mov     rcx, rbp
0x180006fa4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006faa  lea     r8, [rsp+88h+arg_0]
0x180006fb2  mov     rcx, rdi
0x180006fb5  mov     rdx, rax
0x180006fb8  mov     rax, rbx
0x180006fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc0  test    rax, rax
0x180006fc3  jz      short loc_180006FD4
0x180006fc5  movzx   eax, [rsp+88h+arg_0]
0x180006fcd  mov     ebx, [rbp+38h]
0x180006fd0  cmp     eax, ebx
0x180006fd2  ja      short loc_180006FD8
0x180006fd4  inc     esi
0x180006fd6  jmp     short loc_180006F5C
0x180006fd8  test    byte ptr cs:g_dwDebugFlags, 3
0x180006fdf  jz      short loc_180007020
0x180006fe1  mov     rcx, rbp
0x180006fe4  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006fea  mov     rcx, cs:g_pDebug
0x180006ff1  lea     r9, aCheckforheader; "CheckForHeaderRestrictions"
0x180006ff8  mov     [rsp+88h+var_58], ebx
0x180006ffc  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007003  mov     [rsp+88h+var_60], rax
0x180007008  mov     r8d, 610h
0x18000700e  lea     rax, aTheValueOfHead; "The value of header '%s' exceeds %d cha"...
0x180007015  mov     [rsp+88h+var_68], rax
0x18000701a  call    cs:__imp_PuDbgPrint
0x180007020  mov     dword ptr [r15], 1
0x180007027  jmp     short loc_180007030
0x180007029  mov     dword ptr [r15], 0
0x180007030  xor     eax, eax
0x180007032  add     rsp, 48h
0x180007036  pop     r15
0x180007038  pop     r14
0x18000703a  pop     r13
0x18000703c  pop     r12
0x18000703e  pop     rdi
0x18000703f  pop     rsi
0x180007040  pop     rbp
0x180007041  pop     rbx
0x180007042  retn
```
