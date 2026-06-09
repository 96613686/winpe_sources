# GetDeviceMapWorker(void *)

- ea: `0x18003aed0`
- end: `0x18003af42`
- name: `?GetDeviceMapWorker@@YAIPEAX@Z`
- size: `114`
- prototype: `void __fastcall __noreturn(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18003aed0`
- `0x18003d6b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003af3b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003af3b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003aef9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003aef9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003af30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003af30`

## pseudocode

```c
void __fastcall __noreturn GetDeviceMapWorker(unsigned int *a1)
{
  HMODULE v1; // r14
  int v3; // ebp
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v1 = (HMODULE)*((_QWORD *)a1 + 3);
  v3 = 0;
  v6 = 0;
  v5 = CoInitializeEx(0, 2u);
  if ( v5 >= 0 )
  {
    v3 = 1;
    v5 = DeviceMapInitialize(&v6, v4, a1[3], a1 + 8);
    *(_QWORD *)a1 = v6;
    a1[4] = v5;
  }
  _InterlockedExchange((volatile __int32 *)a1 + 2, 1);
  if ( v3 )
    CoUninitialize();
  FreeLibraryAndExitThread(v1, v5);
}

```

## disassembly

```asm
0x18003aed0  mov     [rsp+arg_8], rbx
0x18003aed5  mov     [rsp+arg_10], rbp
0x18003aeda  push    rsi
0x18003aedb  push    rdi
0x18003aedc  push    r14
0x18003aede  sub     rsp, 20h
0x18003aee2  mov     r14, [rcx+18h]
0x18003aee6  mov     rbx, rcx
0x18003aee9  xor     ebp, ebp
0x18003aeeb  mov     [rsp+38h+arg_0], 0
0x18003aef4  xor     ecx, ecx; pvReserved
0x18003aef6  lea     edx, [rbp+2]; dwCoInit
0x18003aef9  call    cs:__imp_CoInitializeEx
0x18003aeff  lea     esi, [rbp+1]
0x18003af02  mov     edi, eax
0x18003af04  test    eax, eax
0x18003af06  js      short loc_18003AF29
0x18003af08  mov     r8d, [rbx+0Ch]
0x18003af0c  lea     r9, [rbx+20h]
0x18003af10  lea     rcx, [rsp+38h+arg_0]
0x18003af15  mov     ebp, esi
0x18003af17  call    DeviceMapInitialize
0x18003af1c  mov     edi, eax
0x18003af1e  mov     rax, [rsp+38h+arg_0]
0x18003af23  mov     [rbx], rax
0x18003af26  mov     [rbx+10h], edi
0x18003af29  xchg    esi, [rbx+8]
0x18003af2c  test    ebp, ebp
0x18003af2e  jz      short loc_18003AF36
0x18003af30  call    cs:__imp_CoUninitialize
0x18003af36  mov     edx, edi; dwExitCode
0x18003af38  mov     rcx, r14; hLibModule
0x18003af3b  call    cs:__imp_FreeLibraryAndExitThread
```
