# W3_CONTEXT::TagRequestForAppWarmup(int *)

- ea: `0x18000ce20`
- end: `0x18000d1b2`
- name: `?TagRequestForAppWarmup@W3_CONTEXT@@AEAAJPEAH@Z`
- size: `914`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aed0`

## callees

- `0x18000ce20`
- `0x180035010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000d1a7`
- `iisutil!PuDbgPrint` at `0x18000d1a7`

## string_xrefs

- `0x18000d19b`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3context.cxx`

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
0x18000ce20  push    rbx
0x18000ce22  push    rbp
0x18000ce23  push    rdi
0x18000ce24  push    r14
0x18000ce26  sub     rsp, 48h
0x18000ce2a  mov     rdi, rcx
0x18000ce2d  mov     r14, rdx
0x18000ce30  mov     rcx, [rcx+2340h]
0x18000ce37  test    rcx, rcx
0x18000ce3a  jnz     loc_18000CF57
0x18000ce40  mov     rax, [rdi+1F98h]
0x18000ce47  xor     ebx, ebx
0x18000ce49  mov     ebp, ebx
0x18000ce4b  cmp     [rax+0DCh], bl
0x18000ce51  jnz     loc_18000CF71
0x18000ce57  mov     rax, [rdi]
0x18000ce5a  lea     r9, [rsp+68h+arg_0]
0x18000ce5f  lea     r8, [rsp+68h+arg_18]
0x18000ce67  mov     [rsp+68h+var_28], rsi
0x18000ce6c  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000ce73  mov     [rsp+68h+arg_18], rbx
0x18000ce7b  mov     rcx, rdi
0x18000ce7e  mov     [rsp+68h+arg_0], ebx
0x18000ce82  mov     rax, [rax+80h]
0x18000ce89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce8e  test    eax, eax
0x18000ce90  jns     loc_18000CF88
0x18000ce96  cmp     eax, 80070585h
0x18000ce9b  jz      loc_18000CF7B
0x18000cea1  mov     rsi, [rsp+68h+var_28]
0x18000cea6  add     rsp, 48h
0x18000ceaa  pop     r14
0x18000ceac  pop     rdi
0x18000cead  pop     rbp
0x18000ceae  pop     rbx
0x18000ceaf  retn
0x18000ceb0  test    rsi, rsi
0x18000ceb3  jz      short loc_18000CEBE
0x18000ceb5  cmp     word ptr [rsi], 30h ; '0'
0x18000ceb9  jnz     short loc_18000CEE2
0x18000cebb  mov     rsi, rbx
0x18000cebe  mov     rax, [rdi]
0x18000cec1  lea     r8, a1; "1"
0x18000cec8  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x18000cecf  mov     rcx, rdi
0x18000ced2  mov     rax, [rax+88h]
0x18000ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cede  test    eax, eax
0x18000cee0  js      short loc_18000CEA1
0x18000cee2  mov     rax, [rdi]
0x18000cee5  lea     r9, [rsp+68h+arg_10]
0x18000ceed  lea     r8, [rsp+68h+var_38]
0x18000cef2  mov     [rsp+68h+var_38], rbx
0x18000cef7  lea     rdx, aSkipManagedMod; "SKIP_MANAGED_MODULES"
0x18000cefe  mov     [rsp+68h+arg_10], ebx
0x18000cf05  mov     rcx, rdi
0x18000cf08  mov     rax, [rax+80h]
0x18000cf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf14  test    eax, eax
0x18000cf16  jns     loc_18000D024
0x18000cf1c  cmp     eax, 80070585h
0x18000cf21  jnz     loc_18000CEA1
0x18000cf27  mov     rax, rbx
0x18000cf2a  mov     [rsp+68h+var_38], rbx
0x18000cf2f  test    rsi, rsi
0x18000cf32  jnz     loc_18000D02E
0x18000cf38  test    rax, rax
0x18000cf3b  jz      loc_18000D0D4
0x18000cf41  cmp     word ptr [rax], 30h ; '0'
0x18000cf45  jz      loc_18000D086
0x18000cf4b  mov     esi, ebx
0x18000cf4d  mov     [r14], esi
0x18000cf50  mov     eax, ebx
0x18000cf52  jmp     loc_18000CEA1
0x18000cf57  mov     rax, [rcx]
0x18000cf5a  xor     edx, edx
0x18000cf5c  mov     rax, [rax+20h]
0x18000cf60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf65  cmp     word ptr [rax], 0
0x18000cf69  jz      loc_18000CE40
0x18000cf6f  xor     ebx, ebx
0x18000cf71  mov     ebp, 1
0x18000cf76  jmp     loc_18000CE57
0x18000cf7b  mov     rsi, rbx
0x18000cf7e  mov     [rsp+68h+arg_18], rbx
0x18000cf86  jmp     short loc_18000CF90
0x18000cf88  mov     rsi, [rsp+68h+arg_18]
0x18000cf90  mov     rcx, [rdi+190h]
0x18000cf97  test    rcx, rcx
0x18000cf9a  jz      loc_18000CEB0
0x18000cfa0  mov     rax, [rcx]
0x18000cfa3  lea     r9, [rsp+68h+arg_0]
0x18000cfa8  lea     r8, [rsp+68h+arg_18]
0x18000cfb0  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000cfb7  mov     rax, [rax+80h]
0x18000cfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc3  test    eax, eax
0x18000cfc5  jns     short loc_18000CFE2
0x18000cfc7  cmp     eax, 80070585h
0x18000cfcc  jnz     loc_18000CEA1
0x18000cfd2  mov     rsi, rbx
0x18000cfd5  mov     [rsp+68h+arg_18], rbx
0x18000cfdd  jmp     loc_18000CEB0
0x18000cfe2  mov     rsi, [rsp+68h+arg_18]
0x18000cfea  test    rsi, rsi
0x18000cfed  jz      loc_18000CEBE
0x18000cff3  mov     rax, [rdi]
0x18000cff6  lea     rdx, aWarmupRequest; "WARMUP_REQUEST"
0x18000cffd  mov     r8, rsi
0x18000d000  mov     rcx, rdi
0x18000d003  mov     rax, [rax+88h]
0x18000d00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00f  test    eax, eax
0x18000d011  js      loc_18000CEA1
0x18000d017  mov     rsi, [rsp+68h+arg_18]
0x18000d01f  jmp     loc_18000CEB0
0x18000d024  mov     rax, [rsp+68h+var_38]
0x18000d029  jmp     loc_18000CF2F
0x18000d02e  cmp     word ptr [rsi], 30h ; '0'
0x18000d032  jz      loc_18000CF38
0x18000d038  mov     esi, ebp
0x18000d03a  test    ebp, ebp
0x18000d03c  jz      loc_18000CF4D
0x18000d042  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d049  jz      loc_18000CF4D
0x18000d04f  mov     rax, [rdi]
0x18000d052  mov     rcx, rdi
0x18000d055  mov     rax, [rax+18h]
0x18000d059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d05e  mov     rdx, rax
0x18000d061  mov     rcx, [rax]
0x18000d064  mov     rax, [rcx+8]
0x18000d068  mov     rcx, rdx
0x18000d06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d070  mov     r8d, 140Bh
0x18000d076  mov     rcx, [rax+58h]
0x18000d07a  lea     rax, aRequestSWarmup; "Request [%S]: WARMUP_REQUEST=1\r\n"
0x18000d081  jmp     loc_18000D188
0x18000d086  mov     esi, ebp
0x18000d088  test    ebp, ebp
0x18000d08a  jz      loc_18000CF4D
0x18000d090  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d097  jz      loc_18000CF4D
0x18000d09d  mov     rax, [rdi]
0x18000d0a0  mov     rcx, rdi
0x18000d0a3  mov     rax, [rax+18h]
0x18000d0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ac  mov     rdx, rax
0x18000d0af  mov     rcx, [rax]
0x18000d0b2  mov     rax, [rcx+8]
0x18000d0b6  mov     rcx, rdx
0x18000d0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0be  mov     r8d, 1418h
0x18000d0c4  mov     rcx, [rax+58h]
0x18000d0c8  lea     rax, aRequestSSkipMa; "Request [%S]: SKIP_MANAGED_MODULES=0\r"...
0x18000d0cf  jmp     loc_18000D188
0x18000d0d4  cmp     qword ptr [rdi+190h], 0
0x18000d0dc  jz      short loc_18000D129
0x18000d0de  mov     esi, ebp
0x18000d0e0  test    ebp, ebp
0x18000d0e2  jz      loc_18000CF4D
0x18000d0e8  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d0ef  jz      loc_18000CF4D
0x18000d0f5  mov     rax, [rdi]
0x18000d0f8  mov     rcx, rdi
0x18000d0fb  mov     rax, [rax+18h]
0x18000d0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d104  mov     rdx, rax
0x18000d107  mov     rcx, [rax]
0x18000d10a  mov     rax, [rcx+8]
0x18000d10e  mov     rcx, rdx
0x18000d111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d116  mov     r8d, 1428h
0x18000d11c  mov     rcx, [rax+58h]
0x18000d120  lea     rax, aRequestSChildR; "Request [%S]: Child request did not set"...
0x18000d127  jmp     short loc_18000D188
0x18000d129  mov     rax, [rdi+1F98h]
0x18000d130  mov     esi, ebx
0x18000d132  cmp     byte ptr [rax+0DEh], 0
0x18000d139  jnz     loc_18000CF4D
0x18000d13f  mov     esi, ebp
0x18000d141  test    ebp, ebp
0x18000d143  jz      loc_18000CF4D
0x18000d149  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d150  jz      loc_18000CF4D
0x18000d156  mov     rax, [rdi]
0x18000d159  mov     rcx, rdi
0x18000d15c  mov     rax, [rax+18h]
0x18000d160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d165  mov     rdx, rax
0x18000d168  mov     rcx, [rax]
0x18000d16b  mov     rax, [rcx+8]
0x18000d16f  mov     rcx, rdx
0x18000d172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d177  mov     r8d, 1433h
0x18000d17d  mov     rcx, [rax+58h]
0x18000d181  lea     rax, aRequestSSkipma; "Request [%S]: skipManagedModules=\"fals"...
0x18000d188  mov     [rsp+68h+var_40], rcx
0x18000d18d  lea     r9, aW3ContextTagre; "W3_CONTEXT::TagRequestForAppWarmup"
0x18000d194  mov     rcx, cs:g_pDebug
0x18000d19b  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000d1a2  mov     [rsp+68h+var_48], rax
0x18000d1a7  call    cs:__imp_PuDbgPrint
0x18000d1ad  jmp     loc_18000CF4D
```
