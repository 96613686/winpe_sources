# CMapsUpdateTaskHandler::WaitForNotification(ulong)

- ea: `0x180007144`
- end: `0x18000719c`
- name: `?WaitForNotification@CMapsUpdateTaskHandler@@AEAAJK@Z`
- size: `88`
- prototype: `DWORD __fastcall(HANDLE *this, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800065c4`

## callees

- `0x18000420c`
- `0x180007144`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007180`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180007180`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007154`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007154`

## string_xrefs

- `0x18000716e`: `CMapsUpdateTaskHandler::WaitForNotification`

## pseudocode

```c
DWORD __fastcall CMapsUpdateTaskHandler::WaitForNotification(HANDLE *this, DWORD a2)
{
  DWORD result; // eax
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  result = WaitForSingleObjectEx(this[12], a2, 0);
  if ( result == 258 )
    return ZTraceReportOrigination(-2147023436, "CMapsUpdateTaskHandler::WaitForNotification", 80, this);
  if ( result )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v4, v5);
  return result;
}

```

## disassembly

```asm
0x180007144  push    rbx
0x180007146  sub     rsp, 20h
0x18000714a  mov     rbx, rcx
0x18000714d  xor     r8d, r8d; bAlertable
0x180007150  mov     rcx, [rcx+60h]; hHandle
0x180007154  call    cs:__imp_WaitForSingleObjectEx
0x18000715a  cmp     eax, 102h
0x18000715f  jz      short loc_18000716B
0x180007161  test    eax, eax
0x180007163  jnz     short loc_18000718C
0x180007165  add     rsp, 20h
0x180007169  pop     rbx
0x18000716a  retn
0x18000716b  mov     r9, rbx
0x18000716e  lea     rdx, aCmapsupdatetas_2; "CMapsUpdateTaskHandler::WaitForNotifica"...
0x180007175  mov     r8d, 50h ; 'P'
0x18000717b  mov     ecx, 800705B4h
0x180007180  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180007186  add     rsp, 20h
0x18000718a  pop     rbx
0x18000718b  retn
0x18000718c  mov     rcx, [rsp+28h]; this
0x180007191  mov     edx, 0B0Fh; void *
0x180007196  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
