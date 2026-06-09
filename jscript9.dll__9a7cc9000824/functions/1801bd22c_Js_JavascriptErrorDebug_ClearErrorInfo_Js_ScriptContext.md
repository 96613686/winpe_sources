# Js::JavascriptErrorDebug::ClearErrorInfo(Js::ScriptContext *)

- ea: `0x1801bd22c`
- end: `0x1801bd2c1`
- name: `?ClearErrorInfo@JavascriptErrorDebug@Js@@SAXPEAVScriptContext@2@@Z`
- size: `149`
- prototype: `void __fastcall(struct Js::ScriptContext *)`
- caller_count: `93`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801ab63c`
- `0x1801abc6c`
- `0x1801bcffc`
- `0x1801bd0f8`
- `0x1801bfff4`
- `0x1801c0b04`
- `0x1801c2010`
- `0x1801c3c54`
- `0x18022b948`
- `0x18022c2bc`
- `0x18022c5f0`
- `0x18023d5d0`
- `0x18023d7a0`
- `0x18023d980`
- `0x18023db20`
- `0x18023dcc0`
- `0x18023de60`
- `0x18023e000`
- `0x18023e1a0`
- `0x18023e340`
- `0x18023e500`
- `0x18023e6b0`
- `0x18023e8b0`
- `0x18023ea60`
- `0x18023ec20`
- `0x18023edf0`
- `0x18023efb0`
- `0x18023f170`
- `0x18023f370`
- `0x18023f570`
- `0x18023f770`
- `0x18023f930`
- `0x18023faf0`
- `0x18023fcc0`
- `0x18023fe90`
- `0x180240040`
- `0x180240210`
- `0x1802403d0`
- `0x180240590`
- `0x180240800`
- `0x1802409c0`
- `0x180240b40`
- `0x180240cc0`
- `0x180240e30`
- `0x180240fa0`
- `0x1802411b0`
- `0x180241330`
- `0x1802414a0`
- `0x180241610`
- `0x180241770`

## callees

- `0x1801bd22c`
- `0x18030f8f0`
- `0x180364010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1801bd269`
- `KERNEL32!LoadLibraryExW` at `0x1801bd269`
- `api-ms-win-downlevel-ole32-l1-1-0!GetErrorInfo` at `0x1801bd299`
- `api-ms-win-downlevel-ole32-l1-1-0!GetErrorInfo` at `0x1801bd299`

## pseudocode

```c
void __fastcall Js::JavascriptErrorDebug::ClearErrorInfo(struct Js::ScriptContext *a1)
{
  Js::DelayLoadWinRtError *v1; // rbx
  const WCHAR *v2; // rax
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-18h] BYREF

  v1 = (Js::DelayLoadWinRtError *)(*((_QWORD *)a1 + 148) + 8480LL);
  if ( !*(_BYTE *)(*((_QWORD *)a1 + 148) + 8496LL) )
  {
    v2 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)a1 + 148) + 8480LL);
    *((_QWORD *)v1 + 1) = LoadLibraryExW(v2, 0, 0x800u);
    *((_BYTE *)v1 + 16) = 1;
  }
  if ( (int)Js::DelayLoadWinRtError::RoClearError(v1) < 0 )
  {
    pperrinfo = 0;
    if ( !GetErrorInfo(0, &pperrinfo) )
      ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x1801bd22c  mov     [rsp+arg_0], rcx
0x1801bd231  push    rbx
0x1801bd232  sub     rsp, 30h
0x1801bd236  mov     rax, [rsp+38h+arg_0]
0x1801bd23b  mov     rbx, [rax+4A0h]
0x1801bd242  add     rbx, 2120h
0x1801bd249  cmp     byte ptr [rbx+10h], 0
0x1801bd24d  jnz     short loc_1801BD27D
0x1801bd24f  mov     rax, [rbx]
0x1801bd252  mov     rcx, rbx
0x1801bd255  mov     rax, [rax+8]
0x1801bd259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bd25e  mov     rcx, rax; lpLibFileName
0x1801bd261  xor     edx, edx; hFile
0x1801bd263  mov     r8d, 800h; dwFlags
0x1801bd269  call    cs:__imp_LoadLibraryExW
0x1801bd270  nop     dword ptr [rax+rax+00h]
0x1801bd275  mov     [rbx+8], rax
0x1801bd279  mov     byte ptr [rbx+10h], 1
0x1801bd27d  mov     rcx, rbx; this
0x1801bd280  call    ?RoClearError@DelayLoadWinRtError@Js@@UEAAJXZ; Js::DelayLoadWinRtError::RoClearError(void)
0x1801bd285  test    eax, eax
0x1801bd287  jns     short loc_1801BD2BA
0x1801bd289  lea     rdx, [rsp+38h+pperrinfo]; pperrinfo
0x1801bd28e  mov     [rsp+38h+pperrinfo], 0
0x1801bd297  xor     ecx, ecx; dwReserved
0x1801bd299  call    cs:__imp_GetErrorInfo
0x1801bd2a0  nop     dword ptr [rax+rax+00h]
0x1801bd2a5  test    eax, eax
0x1801bd2a7  jnz     short loc_1801BD2BA
0x1801bd2a9  mov     rcx, [rsp+38h+pperrinfo]
0x1801bd2ae  mov     rax, [rcx]
0x1801bd2b1  mov     rax, [rax+10h]
0x1801bd2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bd2ba  add     rsp, 30h
0x1801bd2be  pop     rbx
0x1801bd2bf  retn
```
