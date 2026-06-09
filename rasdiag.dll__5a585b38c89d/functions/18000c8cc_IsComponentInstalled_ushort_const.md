# IsComponentInstalled(ushort const *)

- ea: `0x18000c8cc`
- end: `0x18000c9bb`
- name: `?IsComponentInstalled@@YAHPEBG@Z`
- size: `239`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009630`

## callees

- `0x18000c000`
- `0x18000c8cc`
- `0x18000ca8c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c99c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c99c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c8f9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c8f9`

## string_xrefs

- `0x18000c91c`: `IsComponentInstalled: CoInitializeEx failed. 0x%x`

## pseudocode

```c
_BOOL8 __fastcall IsComponentInstalled(const unsigned __int16 *a1)
{
  BOOL v2; // ebx
  HRESULT v3; // edi
  BOOL v4; // edi
  struct INetCfg *v5; // rbx
  int v6; // esi
  struct INetCfg *v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v2 = 1;
  v9 = 0;
  v3 = CoInitializeEx(0, 6u);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147417850 )
  {
    v4 = v3 >= 0;
    if ( (int)HrGetINetCfg(0, (LPVOID *)&v8) >= 0 )
    {
      v5 = v8;
      v6 = ((__int64 (__fastcall *)(struct INetCfg *, const unsigned __int16 *, __int64 *))v8->lpVtbl->FindComponent)(
             v8,
             a1,
             &v9);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      ((void (__fastcall *)(struct INetCfg *))v5->lpVtbl->Uninitialize)(v5);
      ((void (__fastcall *)(struct INetCfg *))v5->lpVtbl->Release)(v5);
      v2 = v6 == 0;
    }
    if ( v4 )
      CoUninitialize();
  }
  else
  {
    RasDiagTrace("IsComponentInstalled: CoInitializeEx failed. 0x%x", v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c8cc  mov     rax, rsp
0x18000c8cf  mov     [rax+8], rbx
0x18000c8d3  mov     [rax+20h], rsi
0x18000c8d7  push    rdi
0x18000c8d8  sub     rsp, 20h
0x18000c8dc  mov     rsi, rcx
0x18000c8df  mov     qword ptr [rax+10h], 0
0x18000c8e7  mov     ebx, 1
0x18000c8ec  mov     qword ptr [rax+18h], 0
0x18000c8f4  xor     ecx, ecx; pvReserved
0x18000c8f6  lea     edx, [rbx+5]; dwCoInit
0x18000c8f9  call    cs:__imp_CoInitializeEx
0x18000c900  nop     dword ptr [rax+rax+00h]
0x18000c905  mov     ecx, 80000000h
0x18000c90a  mov     edi, eax
0x18000c90c  add     eax, ecx
0x18000c90e  test    ecx, eax
0x18000c910  jnz     short loc_18000C92A
0x18000c912  cmp     edi, 80010106h
0x18000c918  jz      short loc_18000C92A
0x18000c91a  mov     edx, edi
0x18000c91c  lea     rcx, aIscomponentins; "IsComponentInstalled: CoInitializeEx fa"...
0x18000c923  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c928  jmp     short loc_18000C9A8
0x18000c92a  not     edi
0x18000c92c  lea     rdx, [rsp+28h+arg_8]; struct INetCfg **
0x18000c931  xor     ecx, ecx; int
0x18000c933  shr     edi, 1Fh
0x18000c936  call    ?HrGetINetCfg@@YAJHPEAPEAUINetCfg@@@Z; HrGetINetCfg(int,INetCfg * *)
0x18000c93b  test    eax, eax
0x18000c93d  js      short loc_18000C998
0x18000c93f  mov     rbx, [rsp+28h+arg_8]
0x18000c944  lea     r8, [rsp+28h+arg_10]
0x18000c949  mov     rdx, rsi
0x18000c94c  mov     rcx, rbx
0x18000c94f  mov     rax, [rbx]
0x18000c952  mov     rax, [rax+40h]
0x18000c956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c95b  mov     rcx, [rsp+28h+arg_10]
0x18000c960  mov     esi, eax
0x18000c962  test    rcx, rcx
0x18000c965  jz      short loc_18000C973
0x18000c967  mov     rax, [rcx]
0x18000c96a  mov     rax, [rax+10h]
0x18000c96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c973  mov     rax, [rbx]
0x18000c976  mov     rcx, rbx
0x18000c979  mov     rax, [rax+20h]
0x18000c97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c982  mov     rax, [rbx]
0x18000c985  mov     rcx, rbx
0x18000c988  mov     rax, [rax+10h]
0x18000c98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c991  xor     ebx, ebx
0x18000c993  test    esi, esi
0x18000c995  setz    bl
0x18000c998  test    edi, edi
0x18000c99a  jz      short loc_18000C9A8
0x18000c99c  call    cs:__imp_CoUninitialize
0x18000c9a3  nop     dword ptr [rax+rax+00h]
0x18000c9a8  mov     rsi, [rsp+28h+arg_18]
0x18000c9ad  mov     eax, ebx
0x18000c9af  mov     rbx, [rsp+28h+arg_0]
0x18000c9b4  add     rsp, 20h
0x18000c9b8  pop     rdi
0x18000c9b9  retn
```
