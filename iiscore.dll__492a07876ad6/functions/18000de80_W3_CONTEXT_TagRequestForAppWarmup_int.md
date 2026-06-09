# W3_CONTEXT::TagRequestForAppWarmup(int *)

- ea: `0x18000de80`
- end: `0x18000e219`
- name: `?TagRequestForAppWarmup@W3_CONTEXT@@AEAAJPEAH@Z`
- size: `921`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bce0`

## callees

- `0x18000de80`
- `0x180038010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000e208`
- `iisutil!PuDbgPrint` at `0x18000e208`

## string_xrefs

- `0x18000e1fc`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3context.cxx`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::TagRequestForAppWarmup(W3_CONTEXT *this, int *a2)
{
  __int64 v4; // rcx
  int v5; // ebp
  __int64 v6; // rax
  __int64 result; // rax
  _WORD *v8; // rsi
  __int64 v9; // rax
  _WORD *v10; // rax
  int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _WORD *v21; // [rsp+30h] [rbp-38h] BYREF
  int v22; // [rsp+70h] [rbp+8h] BYREF
  int v23; // [rsp+80h] [rbp+18h] BYREF
  _WORD *v24; // [rsp+88h] [rbp+20h] BYREF

  v4 = *((_QWORD *)this + 1128);
  if ( v4 && *(_WORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 32LL))(v4, 0)
    || (v5 = 0, *(_BYTE *)(*((_QWORD *)this + 1011) + 220LL)) )
  {
    v5 = 1;
  }
  v6 = *(_QWORD *)this;
  v24 = 0;
  v22 = 0;
  result = (*(__int64 (__fastcall **)(W3_CONTEXT *, const char *, _WORD **, int *))(v6 + 128))(
             this,
             "WARMUP_REQUEST",
             &v24,
             &v22);
  if ( (int)result >= 0 )
  {
    v8 = v24;
  }
  else
  {
    if ( (_DWORD)result != -2147023483 )
      return result;
    v8 = 0;
    v24 = 0;
  }
  v12 = *((_QWORD *)this + 50);
  if ( v12 )
  {
    result = (*(__int64 (__fastcall **)(__int64, const char *, _WORD **, int *))(*(_QWORD *)v12 + 128LL))(
               v12,
               "WARMUP_REQUEST",
               &v24,
               &v22);
    if ( (int)result >= 0 )
    {
      v8 = v24;
      if ( !v24 )
      {
LABEL_9:
        result = (*(__int64 (__fastcall **)(W3_CONTEXT *, const char *, const wchar_t *))(*(_QWORD *)this + 136LL))(
                   this,
                   "APP_WARMING_UP",
                   L"1");
        if ( (int)result < 0 )
          return result;
        goto LABEL_10;
      }
      result = (*(__int64 (__fastcall **)(W3_CONTEXT *, const char *, _WORD *))(*(_QWORD *)this + 136LL))(
                 this,
                 "WARMUP_REQUEST",
                 v24);
      if ( (int)result < 0 )
        return result;
      v8 = v24;
    }
    else
    {
      if ( (_DWORD)result != -2147023483 )
        return result;
      v8 = 0;
      v24 = 0;
    }
  }
  if ( !v8 )
    goto LABEL_9;
  if ( *v8 == 48 )
  {
    v8 = 0;
    goto LABEL_9;
  }
LABEL_10:
  v9 = *(_QWORD *)this;
  v21 = 0;
  v23 = 0;
  result = (*(__int64 (__fastcall **)(W3_CONTEXT *, const char *, _WORD **, int *))(v9 + 128))(
             this,
             "SKIP_MANAGED_MODULES",
             &v21,
             &v23);
  if ( (int)result >= 0 )
  {
    v10 = v21;
  }
  else
  {
    if ( (_DWORD)result != -2147023483 )
      return result;
    v10 = 0;
    v21 = 0;
  }
  if ( !v8 || *v8 == 48 )
  {
    if ( v10 )
    {
      if ( *v10 == 48 )
      {
        v11 = v5;
        if ( v5 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v15 = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 24LL))(this);
            v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3context.cxx",
              5144,
              "W3_CONTEXT::TagRequestForAppWarmup",
              "Request [%S]: SKIP_MANAGED_MODULES=0\r\n",
              *(_QWORD *)(v16 + 88));
          }
        }
      }
      else
      {
        v11 = 0;
      }
    }
    else if ( *((_QWORD *)this + 50) )
    {
      v11 = v5;
      if ( v5 && (g_dwDebugFlags & 3) != 0 )
      {
        v17 = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 24LL))(this);
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3context.cxx",
          5160,
          "W3_CONTEXT::TagRequestForAppWarmup",
          "Request [%S]: Child request did not set SKIP_MANAGED_MODULES\r\n",
          *(_QWORD *)(v18 + 88));
      }
    }
    else
    {
      v11 = 0;
      if ( !*(_BYTE *)(*((_QWORD *)this + 1011) + 222LL) )
      {
        v11 = v5;
        if ( v5 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            v19 = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 24LL))(this);
            v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3context.cxx",
              5171,
              "W3_CONTEXT::TagRequestForAppWarmup",
              "Request [%S]: skipManagedModules=\"false\"\r\n",
              *(_QWORD *)(v20 + 88));
          }
        }
      }
    }
  }
  else
  {
    v11 = v5;
    if ( v5 && (g_dwDebugFlags & 3) != 0 )
    {
      v13 = (*(__int64 (__fastcall **)(W3_CONTEXT *))(*(_QWORD *)this + 24LL))(this);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3context.cxx",
        5131,
        "W3_CONTEXT::TagRequestForAppWarmup",
        "Request [%S]: WARMUP_REQUEST=1\r\n",
        *(_QWORD *)(v14 + 88));
    }
  }
  *a2 = v11;
  return 0;
}

```

## disassembly

```asm
0x18000de80  push    rbx
0x18000de82  push    rbp
0x18000de83  push    rdi
0x18000de84  push    r14
0x18000de86  sub     rsp, 48h
0x18000de8a  mov     rdi, rcx
0x18000de8d  mov     r14, rdx
0x18000de90  mov     rcx, [rcx+2340h]
0x18000de97  test    rcx, rcx
0x18000de9a  jnz     loc_18000DFB8
0x18000dea0  mov     rax, [rdi+1F98h]
0x18000dea7  xor     ebx, ebx
0x18000dea9  mov     ebp, ebx
0x18000deab  cmp     [rax+0DCh], bl
0x18000deb1  jnz     loc_18000DFD2
0x18000deb7  mov     rax, [rdi]
0x18000deba  lea     r9, [rsp+68h+arg_0]
0x18000debf  lea     r8, [rsp+68h+arg_18]
0x18000dec7  mov     [rsp+68h+var_28], rsi
0x18000decc  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000ded3  mov     [rsp+68h+arg_18], rbx
0x18000dedb  mov     rcx, rdi
0x18000dede  mov     [rsp+68h+arg_0], ebx
0x18000dee2  mov     rax, [rax+80h]
0x18000dee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deee  test    eax, eax
0x18000def0  jns     loc_18000DFE9
0x18000def6  cmp     eax, 80070585h
0x18000defb  jz      loc_18000DFDC
0x18000df01  mov     rsi, [rsp+68h+var_28]
0x18000df06  add     rsp, 48h
0x18000df0a  pop     r14
0x18000df0c  pop     rdi
0x18000df0d  pop     rbp
0x18000df0e  pop     rbx
0x18000df0f  retn
0x18000df11  test    rsi, rsi
0x18000df14  jz      short loc_18000DF1F
0x18000df16  cmp     word ptr [rsi], 30h ; '0'
0x18000df1a  jnz     short loc_18000DF43
0x18000df1c  mov     rsi, rbx
0x18000df1f  mov     rax, [rdi]
0x18000df22  lea     r8, a1; "1"
0x18000df29  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x18000df30  mov     rcx, rdi
0x18000df33  mov     rax, [rax+88h]
0x18000df3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df3f  test    eax, eax
0x18000df41  js      short loc_18000DF01
0x18000df43  mov     rax, [rdi]
0x18000df46  lea     r9, [rsp+68h+arg_10]
0x18000df4e  lea     r8, [rsp+68h+var_38]
0x18000df53  mov     [rsp+68h+var_38], rbx
0x18000df58  lea     rdx, aSkipManagedMod; "SKIP_MANAGED_MODULES"
0x18000df5f  mov     [rsp+68h+arg_10], ebx
0x18000df66  mov     rcx, rdi
0x18000df69  mov     rax, [rax+80h]
0x18000df70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df75  test    eax, eax
0x18000df77  jns     loc_18000E085
0x18000df7d  cmp     eax, 80070585h
0x18000df82  jnz     loc_18000DF01
0x18000df88  mov     rax, rbx
0x18000df8b  mov     [rsp+68h+var_38], rbx
0x18000df90  test    rsi, rsi
0x18000df93  jnz     loc_18000E08F
0x18000df99  test    rax, rax
0x18000df9c  jz      loc_18000E135
0x18000dfa2  cmp     word ptr [rax], 30h ; '0'
0x18000dfa6  jz      loc_18000E0E7
0x18000dfac  mov     esi, ebx
0x18000dfae  mov     [r14], esi
0x18000dfb1  mov     eax, ebx
0x18000dfb3  jmp     loc_18000DF01
0x18000dfb8  mov     rax, [rcx]
0x18000dfbb  xor     edx, edx
0x18000dfbd  mov     rax, [rax+20h]
0x18000dfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfc6  cmp     word ptr [rax], 0
0x18000dfca  jz      loc_18000DEA0
0x18000dfd0  xor     ebx, ebx
0x18000dfd2  mov     ebp, 1
0x18000dfd7  jmp     loc_18000DEB7
0x18000dfdc  mov     rsi, rbx
0x18000dfdf  mov     [rsp+68h+arg_18], rbx
0x18000dfe7  jmp     short loc_18000DFF1
0x18000dfe9  mov     rsi, [rsp+68h+arg_18]
0x18000dff1  mov     rcx, [rdi+190h]
0x18000dff8  test    rcx, rcx
0x18000dffb  jz      loc_18000DF11
0x18000e001  mov     rax, [rcx]
0x18000e004  lea     r9, [rsp+68h+arg_0]
0x18000e009  lea     r8, [rsp+68h+arg_18]
0x18000e011  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000e018  mov     rax, [rax+80h]
0x18000e01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e024  test    eax, eax
0x18000e026  jns     short loc_18000E043
0x18000e028  cmp     eax, 80070585h
0x18000e02d  jnz     loc_18000DF01
0x18000e033  mov     rsi, rbx
0x18000e036  mov     [rsp+68h+arg_18], rbx
0x18000e03e  jmp     loc_18000DF11
0x18000e043  mov     rsi, [rsp+68h+arg_18]
0x18000e04b  test    rsi, rsi
0x18000e04e  jz      loc_18000DF1F
0x18000e054  mov     rax, [rdi]
0x18000e057  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000e05e  mov     r8, rsi
0x18000e061  mov     rcx, rdi
0x18000e064  mov     rax, [rax+88h]
0x18000e06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e070  test    eax, eax
0x18000e072  js      loc_18000DF01
0x18000e078  mov     rsi, [rsp+68h+arg_18]
0x18000e080  jmp     loc_18000DF11
0x18000e085  mov     rax, [rsp+68h+var_38]
0x18000e08a  jmp     loc_18000DF90
0x18000e08f  cmp     word ptr [rsi], 30h ; '0'
0x18000e093  jz      loc_18000DF99
0x18000e099  mov     esi, ebp
0x18000e09b  test    ebp, ebp
0x18000e09d  jz      loc_18000DFAE
0x18000e0a3  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e0aa  jz      loc_18000DFAE
0x18000e0b0  mov     rax, [rdi]
0x18000e0b3  mov     rcx, rdi
0x18000e0b6  mov     rax, [rax+18h]
0x18000e0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0bf  mov     rdx, rax
0x18000e0c2  mov     rcx, [rax]
0x18000e0c5  mov     rax, [rcx+8]
0x18000e0c9  mov     rcx, rdx
0x18000e0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d1  mov     r8d, 140Bh
0x18000e0d7  mov     rcx, [rax+58h]
0x18000e0db  lea     rax, aRequestSWarmup; "Request [%S]: WARMUP_REQUEST=1\r\n"
0x18000e0e2  jmp     loc_18000E1E9
0x18000e0e7  mov     esi, ebp
0x18000e0e9  test    ebp, ebp
0x18000e0eb  jz      loc_18000DFAE
0x18000e0f1  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e0f8  jz      loc_18000DFAE
0x18000e0fe  mov     rax, [rdi]
0x18000e101  mov     rcx, rdi
0x18000e104  mov     rax, [rax+18h]
0x18000e108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e10d  mov     rdx, rax
0x18000e110  mov     rcx, [rax]
0x18000e113  mov     rax, [rcx+8]
0x18000e117  mov     rcx, rdx
0x18000e11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11f  mov     r8d, 1418h
0x18000e125  mov     rcx, [rax+58h]
0x18000e129  lea     rax, aRequestSSkipMa; "Request [%S]: SKIP_MANAGED_MODULES=0\r"...
0x18000e130  jmp     loc_18000E1E9
0x18000e135  cmp     qword ptr [rdi+190h], 0
0x18000e13d  jz      short loc_18000E18A
0x18000e13f  mov     esi, ebp
0x18000e141  test    ebp, ebp
0x18000e143  jz      loc_18000DFAE
0x18000e149  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e150  jz      loc_18000DFAE
0x18000e156  mov     rax, [rdi]
0x18000e159  mov     rcx, rdi
0x18000e15c  mov     rax, [rax+18h]
0x18000e160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e165  mov     rdx, rax
0x18000e168  mov     rcx, [rax]
0x18000e16b  mov     rax, [rcx+8]
0x18000e16f  mov     rcx, rdx
0x18000e172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e177  mov     r8d, 1428h
0x18000e17d  mov     rcx, [rax+58h]
0x18000e181  lea     rax, aRequestSChildR; "Request [%S]: Child request did not set"...
0x18000e188  jmp     short loc_18000E1E9
0x18000e18a  mov     rax, [rdi+1F98h]
0x18000e191  mov     esi, ebx
0x18000e193  cmp     byte ptr [rax+0DEh], 0
0x18000e19a  jnz     loc_18000DFAE
0x18000e1a0  mov     esi, ebp
0x18000e1a2  test    ebp, ebp
0x18000e1a4  jz      loc_18000DFAE
0x18000e1aa  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e1b1  jz      loc_18000DFAE
0x18000e1b7  mov     rax, [rdi]
0x18000e1ba  mov     rcx, rdi
0x18000e1bd  mov     rax, [rax+18h]
0x18000e1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c6  mov     rdx, rax
0x18000e1c9  mov     rcx, [rax]
0x18000e1cc  mov     rax, [rcx+8]
0x18000e1d0  mov     rcx, rdx
0x18000e1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d8  mov     r8d, 1433h
0x18000e1de  mov     rcx, [rax+58h]
0x18000e1e2  lea     rax, aRequestSSkipma; "Request [%S]: skipManagedModules=\"fals"...
0x18000e1e9  mov     [rsp+68h+var_40], rcx
0x18000e1ee  lea     r9, aW3ContextTagre; "W3_CONTEXT::TagRequestForAppWarmup"
0x18000e1f5  mov     rcx, cs:g_pDebug
0x18000e1fc  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000e203  mov     [rsp+68h+var_48], rax
0x18000e208  call    cs:__imp_PuDbgPrint
0x18000e20f  nop     dword ptr [rax+rax+00h]
0x18000e214  jmp     loc_18000DFAE
```
