# CMapsUpdateTaskHandler::UpdateCheckResultCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180006e70`
- end: `0x180006edc`
- name: `?UpdateCheckResultCallback@CMapsUpdateTaskHandler@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `108`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, char *, _OWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180006e70`
- `0x1800075e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ebb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ebb`

## pseudocode

```c
__int64 __fastcall CMapsUpdateTaskHandler::UpdateCheckResultCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        char *a4,
        _OWORD *a5,
        unsigned int a6)
{
  __int128 v6; // xmm0
  void *v7; // rcx
  __int128 v8; // xmm1
  unsigned int v9; // r8d
  const char *v10; // r9
  __int128 v12; // [rsp+24h] [rbp-24h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a6 != 32 )
    __int2c();
  if ( !a4 )
    __int2c();
  if ( *(_DWORD *)a5 == 1 )
  {
    v6 = *(_OWORD *)((char *)a5 + 4);
    v7 = (void *)*((_QWORD *)a4 + 12);
    v8 = a5[1];
    *((_DWORD *)a4 + 16) = 1;
    v12 = v6;
    HIDWORD(v12) = v8;
    *(_OWORD *)(a4 + 68) = v12;
    *((_OWORD *)a4 + 5) = v8;
    if ( !SetEvent(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180006e70  sub     rsp, 48h
0x180006e74  cmp     [rsp+48h+arg_28], 20h ; ' '
0x180006e79  jz      short loc_180006E7D
0x180006e7b  int     2Ch; Windows NT - assertion failure
0x180006e7d  mov     rax, [rsp+48h+arg_20]
0x180006e82  test    r9, r9
0x180006e85  jnz     short loc_180006E89
0x180006e87  int     2Ch; Windows NT - assertion failure
0x180006e89  cmp     dword ptr [rax], 1
0x180006e8c  jnz     short loc_180006EC5
0x180006e8e  movups  xmm0, xmmword ptr [rax+4]
0x180006e92  mov     rcx, [r9+60h]; hEvent
0x180006e96  movups  xmm1, xmmword ptr [rax+10h]
0x180006e9a  mov     dword ptr [r9+40h], 1
0x180006ea2  movups  [rsp+48h+var_24], xmm0
0x180006ea7  movaps  [rsp+48h+var_24+0Ch], xmm1
0x180006eac  movups  xmm0, [rsp+48h+var_24]
0x180006eb1  movups  xmmword ptr [r9+44h], xmm0
0x180006eb6  movups  xmmword ptr [r9+50h], xmm1
0x180006ebb  call    cs:__imp_SetEvent
0x180006ec1  test    eax, eax
0x180006ec3  jz      short loc_180006ECC
0x180006ec5  xor     eax, eax
0x180006ec7  add     rsp, 48h
0x180006ecb  retn
0x180006ecc  mov     rcx, [rsp+48h]; this
0x180006ed1  mov     edx, 0A01h; void *
0x180006ed6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
