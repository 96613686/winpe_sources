# UtilLoadStringWithAlloc(uint,ushort * *,uint)

- ea: `0x1800071ec`
- end: `0x18000728c`
- name: `?UtilLoadStringWithAlloc@@YAJIPEAPEAGI@Z`
- size: `160`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800070d4`

## callees

- `0x1800040b4`
- `0x1800071ec`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000722d`
- `KERNEL32!GetModuleHandleW` at `0x18000722d`
- `KERNEL32!GetLastError` at `0x18000724b`
- `KERNEL32!GetLastError` at `0x18000724b`
- `USER32!LoadStringW` at `0x180007241`
- `USER32!LoadStringW` at `0x180007241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007211`

## pseudocode

```c
__int64 __fastcall UtilLoadStringWithAlloc(UINT uID, unsigned __int16 **a2)
{
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rbx
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v10 = v5;
  ModuleHandleW = GetModuleHandleW(0);
  if ( LoadStringW(ModuleHandleW, uID, v6, 1024) )
  {
    *a2 = v6;
    v9 = 0;
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>::~TSimpleDeallocator<unsigned short *,void,void *,&void CoTaskMemFree(void *)>((void **)&v10);
  return v9;
}

```

## disassembly

```asm
0x1800071ec  mov     [rsp+arg_0], rbx
0x1800071f1  mov     [rsp+arg_10], rsi
0x1800071f6  push    rdi
0x1800071f7  sub     rsp, 20h
0x1800071fb  mov     rdi, rdx
0x1800071fe  mov     esi, ecx
0x180007200  test    rdx, rdx
0x180007203  jnz     short loc_18000720C
0x180007205  mov     eax, 80070057h
0x18000720a  jmp     short loc_18000727C
0x18000720c  mov     ecx, 800h; cb
0x180007211  call    cs:__imp_CoTaskMemAlloc
0x180007217  mov     rbx, rax
0x18000721a  test    rax, rax
0x18000721d  jnz     short loc_180007226
0x18000721f  mov     eax, 8007000Eh
0x180007224  jmp     short loc_18000727C
0x180007226  xor     ecx, ecx; lpModuleName
0x180007228  mov     [rsp+28h+arg_8], rbx
0x18000722d  call    cs:__imp_GetModuleHandleW
0x180007233  mov     r9d, 400h; cchBufferMax
0x180007239  mov     r8, rbx; lpBuffer
0x18000723c  mov     rcx, rax; hInstance
0x18000723f  mov     edx, esi; uID
0x180007241  call    cs:__imp_LoadStringW
0x180007247  test    eax, eax
0x180007249  jnz     short loc_180007262
0x18000724b  call    cs:__imp_GetLastError
0x180007251  mov     ebx, eax
0x180007253  test    eax, eax
0x180007255  jle     short loc_180007270
0x180007257  movzx   ebx, ax
0x18000725a  or      ebx, 80070000h
0x180007260  jmp     short loc_180007270
0x180007262  mov     [rdi], rbx
0x180007265  xor     ebx, ebx
0x180007267  mov     [rsp+28h+arg_8], 0
0x180007270  lea     rcx, [rsp+28h+arg_8]
0x180007275  call    ??1?$TSimpleDeallocator@PEAGXPEAX$1?CoTaskMemFree@@YAXPEAX@Z@@QEAA@XZ; TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>::~TSimpleDeallocator<ushort *,void,void *,&CoTaskMemFree(void *)>(void)
0x18000727a  mov     eax, ebx
0x18000727c  mov     rbx, [rsp+28h+arg_0]
0x180007281  mov     rsi, [rsp+28h+arg_10]
0x180007286  add     rsp, 20h
0x18000728a  pop     rdi
0x18000728b  retn
```
