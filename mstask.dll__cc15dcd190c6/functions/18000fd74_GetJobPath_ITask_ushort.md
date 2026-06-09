# GetJobPath(ITask *,ushort * *)

- ea: `0x18000fd74`
- end: `0x18000fe1e`
- name: `?GetJobPath@@YAJPEAUITask@@PEAPEAG@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct ITask *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800105a8`
- `0x180012fe8`
- `0x180016e14`

## callees

- `0x18000fd74`
- `0x1800101b4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fde1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fde1`

## pseudocode

```c
__int64 __fastcall GetJobPath(struct ITask *a1, unsigned __int16 **a2)
{
  struct ITaskVtbl *lpVtbl; // rax
  int v4; // ebx
  unsigned __int16 *v5; // rdi
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  lpVtbl = a1->lpVtbl;
  pv = 0;
  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct ITask *, GUID *, __int64 *))lpVtbl->QueryInterface)(a1, &IID_IPersistFile, &v8);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 64LL))(v8, &pv);
    if ( v4 >= 0 )
    {
      v5 = NewDupString((const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
      if ( v5 )
        *a2 = v5;
      else
        v4 = -2147024882;
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fd74  mov     r11, rsp
0x18000fd77  mov     [r11+10h], rbx
0x18000fd7b  mov     [r11+20h], rsi
0x18000fd7f  push    rdi
0x18000fd80  sub     rsp, 20h
0x18000fd84  mov     rax, [rcx]
0x18000fd87  lea     r8, [r11+18h]
0x18000fd8b  mov     rsi, rdx
0x18000fd8e  mov     qword ptr [r11+8], 0
0x18000fd96  lea     rdx, IID_IPersistFile
0x18000fd9d  mov     qword ptr [r11+18h], 0
0x18000fda5  mov     rax, [rax]
0x18000fda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdad  mov     ebx, eax
0x18000fdaf  test    eax, eax
0x18000fdb1  js      short loc_18000FDF6
0x18000fdb3  mov     rcx, [rsp+28h+arg_10]
0x18000fdb8  lea     rdx, [rsp+28h+pv]
0x18000fdbd  mov     rax, [rcx]
0x18000fdc0  mov     rax, [rax+40h]
0x18000fdc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdc9  mov     ebx, eax
0x18000fdcb  test    eax, eax
0x18000fdcd  js      short loc_18000FDF6
0x18000fdcf  mov     rcx, [rsp+28h+pv]; Src
0x18000fdd4  call    ?NewDupString@@YAPEAGPEBG@Z; NewDupString(ushort const *)
0x18000fdd9  mov     rcx, [rsp+28h+pv]; pv
0x18000fdde  mov     rdi, rax
0x18000fde1  call    cs:__imp_CoTaskMemFree
0x18000fde7  test    rdi, rdi
0x18000fdea  jnz     short loc_18000FDF3
0x18000fdec  mov     ebx, 8007000Eh
0x18000fdf1  jmp     short loc_18000FDF6
0x18000fdf3  mov     [rsi], rdi
0x18000fdf6  mov     rcx, [rsp+28h+arg_10]
0x18000fdfb  test    rcx, rcx
0x18000fdfe  jz      short loc_18000FE0C
0x18000fe00  mov     rax, [rcx]
0x18000fe03  mov     rax, [rax+10h]
0x18000fe07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe0c  mov     rsi, [rsp+28h+arg_18]
0x18000fe11  mov     eax, ebx
0x18000fe13  mov     rbx, [rsp+28h+arg_8]
0x18000fe18  add     rsp, 20h
0x18000fe1c  pop     rdi
0x18000fe1d  retn
```
