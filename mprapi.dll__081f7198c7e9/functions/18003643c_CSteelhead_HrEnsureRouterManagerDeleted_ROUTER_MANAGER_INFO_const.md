# CSteelhead::HrEnsureRouterManagerDeleted(ROUTER_MANAGER_INFO const &)

- ea: `0x18003643c`
- end: `0x1800364ee`
- name: `?HrEnsureRouterManagerDeleted@CSteelhead@@IEAAJAEBUROUTER_MANAGER_INFO@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(void **this, const struct ROUTER_MANAGER_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180036c94`

## callees

- `0x180028100`
- `0x18003643c`
- `0x1800364f4`

## import_xrefs

- `rtutils!TracePrintfW` at `0x18003649f`
- `rtutils!TracePrintfW` at `0x1800364db`
- `rtutils!TracePrintfW` at `0x18003649f`
- `rtutils!TracePrintfW` at `0x1800364db`

## string_xrefs

- `0x1800364d4`: `CSteelhead::HrEnsureRouterManagerDeleted`
- `0x18003648e`: `HrMprConfigTransportDelete`

## pseudocode

```c
__int64 __fastcall CSteelhead::HrEnsureRouterManagerDeleted(void **this, const struct ROUTER_MANAGER_INFO *a2)
{
  unsigned int v2; // edx
  int Handle; // ebx
  signed int v5; // eax
  bool v6; // sf
  __int64 v7; // r9
  HANDLE hRouterTransport; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_DWORD *)a2;
  hRouterTransport = 0;
  Handle = HrMprConfigTransportGetHandle(this[13], v2, &hRouterTransport);
  if ( Handle >= 0 )
  {
    v5 = MprConfigTransportDelete(this[13], hRouterTransport);
    v6 = v5 < 0;
    if ( v5 )
    {
      if ( v5 > 0 )
      {
        v5 = (unsigned __int16)v5 | 0x80070000;
        v6 = v5 < 0;
      }
      if ( v6 )
      {
        TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrMprConfigTransportDelete", (unsigned int)v5);
LABEL_10:
        v7 = (unsigned int)Handle;
        goto LABEL_11;
      }
    }
LABEL_9:
    if ( Handle < 0 )
    {
      TracePrintfW(
        g_dwTraceHandle,
        L"%hs failed : hr = %08lx",
        "CSteelhead::HrEnsureRouterManagerDeleted",
        (unsigned int)Handle);
      return (unsigned int)Handle;
    }
    goto LABEL_10;
  }
  if ( Handle != -2147023994 )
    goto LABEL_9;
  v7 = 0;
LABEL_11:
  TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "CSteelhead::HrEnsureRouterManagerDeleted", v7);
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x18003643c  mov     [rsp+arg_8], rbx
0x180036441  push    rdi
0x180036442  sub     rsp, 20h
0x180036446  mov     edx, [rdx]; unsigned int
0x180036448  lea     r8, [rsp+28h+hRouterTransport]; void **
0x18003644d  mov     rdi, rcx
0x180036450  mov     [rsp+28h+hRouterTransport], 0
0x180036459  mov     rcx, [rcx+68h]; void *
0x18003645d  call    ?HrMprConfigTransportGetHandle@@YAJPEAXKPEAPEAX@Z; HrMprConfigTransportGetHandle(void *,ulong,void * *)
0x180036462  mov     ebx, eax
0x180036464  test    eax, eax
0x180036466  js      short loc_1800364A7
0x180036468  mov     rdx, [rsp+28h+hRouterTransport]; hRouterTransport
0x18003646d  mov     rcx, [rdi+68h]; hMprConfig
0x180036471  call    MprConfigTransportDelete
0x180036476  test    eax, eax
0x180036478  jz      short loc_1800364B4
0x18003647a  jle     short loc_180036486
0x18003647c  movzx   eax, ax
0x18003647f  or      eax, 80070000h
0x180036484  test    eax, eax
0x180036486  jns     short loc_1800364B4
0x180036488  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x18003648e  lea     r8, aHrmprconfigtra_1; "HrMprConfigTransportDelete"
0x180036495  mov     r9d, eax
0x180036498  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x18003649f  call    cs:__imp_TracePrintfW
0x1800364a5  jmp     short loc_1800364B8
0x1800364a7  cmp     ebx, 80070386h
0x1800364ad  jnz     short loc_1800364B4
0x1800364af  xor     r9d, r9d
0x1800364b2  jmp     short loc_1800364BB
0x1800364b4  test    ebx, ebx
0x1800364b6  js      short loc_1800364C4
0x1800364b8  mov     r9d, ebx
0x1800364bb  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x1800364c2  jmp     short loc_1800364CE
0x1800364c4  mov     r9d, ebx
0x1800364c7  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x1800364ce  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x1800364d4  lea     r8, aCsteelheadHren_1; "CSteelhead::HrEnsureRouterManagerDelete"...
0x1800364db  call    cs:__imp_TracePrintfW
0x1800364e1  mov     eax, ebx
0x1800364e3  mov     rbx, [rsp+28h+arg_8]
0x1800364e8  add     rsp, 20h
0x1800364ec  pop     rdi
0x1800364ed  retn
```
