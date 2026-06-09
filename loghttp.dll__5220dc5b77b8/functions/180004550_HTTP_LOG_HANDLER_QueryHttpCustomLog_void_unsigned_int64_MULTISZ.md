# HTTP_LOG_HANDLER::QueryHttpCustomLog(void *,unsigned __int64,MULTISZ * *)

- ea: `0x180004550`
- end: `0x18000462e`
- name: `?QueryHttpCustomLog@HTTP_LOG_HANDLER@@SAJPEAX_KPEAPEAVMULTISZ@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_DWORD *, __int64, struct MULTISZ **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f40`

## callees

- `0x180004550`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800045c7`
- `iisutil!PuDbgPrint` at `0x1800045c7`

## string_xrefs

- `0x1800045b9`: `servercommon\inetsrv\iis\iisrearc\iis70\httplog\httplog.cxx`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_HANDLER::QueryHttpCustomLog(_DWORD *a1, __int64 a2, struct MULTISZ **a3)
{
  int v4; // ecx
  _DWORD **v5; // rdx
  void **v6; // r9

  if ( !a1 )
  {
    v4 = -2147024809;
LABEL_11:
    *a3 = 0;
    return (unsigned int)v4;
  }
  v4 = 0;
  if ( a1[6] != 1145854021 )
    v4 = -2147024809;
  if ( v4 < 0 )
    goto LABEL_11;
  if ( *((_QWORD *)a1 + 4) != a2 )
  {
    v4 = -2147024809;
    goto LABEL_11;
  }
  v5 = (_DWORD **)*((_QWORD *)a1 + 1);
  if ( v5[1] != a1 + 2 || (v6 = (void **)*((_QWORD *)a1 + 2), *v6 != a1 + 2) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  *a3 = (struct MULTISZ *)(a1 + 10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004550  mov     [rsp+arg_10], r8
0x180004555  mov     [rsp+arg_8], rdx
0x18000455a  mov     [rsp+arg_0], rcx
0x18000455f  push    rbx
0x180004560  sub     rsp, 40h
0x180004564  mov     rbx, rcx
0x180004567  test    rcx, rcx
0x18000456a  jnz     short loc_180004576
0x18000456c  mov     ecx, 80070057h
0x180004571  jmp     loc_180004618
0x180004576  xor     ecx, ecx
0x180004578  mov     eax, 80070057h
0x18000457d  cmp     dword ptr [rbx+18h], 444C5845h
0x180004584  cmovnz  ecx, eax
0x180004587  mov     [rsp+48h+var_18], ecx
0x18000458b  jmp     short loc_1800045E2
0x18000458d  mov     rbx, [rsp+48h+arg_0]
0x180004592  test    byte ptr cs:g_dwDebugFlags, 3
0x180004599  jz      short loc_1800045CD
0x18000459b  mov     [rsp+48h+var_20], rbx
0x1800045a0  lea     rax, aHeapErrorP; "Heap error %p \n"
0x1800045a7  mov     [rsp+48h+var_28], rax
0x1800045ac  lea     r9, aHttpLogHandler; "HTTP_LOG_HANDLER::QueryHttpCustomLog"
0x1800045b3  mov     r8d, 524h
0x1800045b9  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800045c0  mov     rcx, cs:g_pDebug
0x1800045c7  call    cs:__imp_PuDbgPrint
0x1800045cd  mov     ecx, 80070057h
0x1800045d2  mov     [rsp+48h+var_18], ecx
0x1800045d6  mov     eax, ecx
0x1800045d8  mov     r8, [rsp+48h+arg_10]
0x1800045dd  mov     rdx, [rsp+48h+arg_8]
0x1800045e2  test    ecx, ecx
0x1800045e4  js      short loc_180004618
0x1800045e6  cmp     [rbx+20h], rdx
0x1800045ea  jz      short loc_1800045F0
0x1800045ec  mov     ecx, eax
0x1800045ee  jmp     short loc_180004618
0x1800045f0  lea     rax, [rbx+8]
0x1800045f4  mov     rdx, [rax]
0x1800045f7  cmp     [rdx+8], rax
0x1800045fb  jnz     short loc_180004627
0x1800045fd  mov     r9, [rax+8]
0x180004601  cmp     [r9], rax
0x180004604  jnz     short loc_180004627
0x180004606  mov     [r9], rdx
0x180004609  mov     [rdx+8], r9
0x18000460d  lea     rax, [rbx+28h]
0x180004611  mov     [r8], rax
0x180004614  test    ecx, ecx
0x180004616  jns     short loc_18000461F
0x180004618  mov     qword ptr [r8], 0
0x18000461f  mov     eax, ecx
0x180004621  add     rsp, 40h
0x180004625  pop     rbx
0x180004626  retn
0x180004627  mov     ecx, 3
0x18000462c  int     29h; Win8: RtlFailFast(ecx)
```
