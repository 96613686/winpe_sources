# CSyncHandler::GetName(ushort * *)

- ea: `0x180003950`
- end: `0x180003a82`
- name: `?GetName@CSyncHandler@@UEAAJPEAPEAG@Z`
- size: `306`
- prototype: `__int64 __fastcall(CSyncHandler *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x180003a90`
- `0x180008b40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003a4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800039b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800039b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a18`

## pseudocode

```c
__int64 __fastcall CSyncHandler::GetName(CSyncHandler *this, LPVOID *a2)
{
  __int64 result; // rax
  unsigned __int16 *v4; // rbx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  int v11; // ebx
  void *v12; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+18h] BYREF

  lpMem = 0;
  result = CscUtil_FormatStringID((LPWSTR)&lpMem, g_hInstance, 0x2Du);
  if ( (int)result < 0 )
    return result;
  v4 = (unsigned __int16 *)lpMem;
  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)lpMem + v5) );
  v6 = v5 + 1;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
  *a2 = v7;
  v8 = v7;
  if ( v7 )
  {
    if ( v6 )
    {
      if ( v6 > 0x7FFFFFFF )
      {
        v11 = -2147024809;
        *v7 = 0;
LABEL_15:
        CoTaskMemFree(*a2);
        *a2 = 0;
        goto LABEL_19;
      }
      v9 = 2147483646;
      do
      {
        if ( !v9 )
          break;
        if ( !*v4 )
          break;
        *v8++ = *v4++;
        --v9;
        --v6;
      }
      while ( v6 );
      v10 = v8 - 1;
      v11 = -2147024774;
      if ( v6 )
      {
        v10 = v8;
        v11 = 0;
      }
      *v10 = 0;
    }
    else
    {
      v11 = -2147024809;
    }
    if ( v11 >= 0 )
      goto LABEL_19;
    goto LABEL_15;
  }
  v11 = -2147024882;
LABEL_19:
  v12 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
    {
      if ( !HeapFree(ProcessHeap, 0, v12) )
        ResultFromLastError();
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003950  push    rsi
0x180003952  sub     rsp, 20h
0x180003956  mov     rsi, rdx
0x180003959  mov     [rsp+28h+lpMem], 0
0x180003962  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180003969  lea     rcx, [rsp+28h+lpMem]; lpBuffer
0x18000396e  mov     r8d, 2Dh ; '-'; uID
0x180003974  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x180003979  test    eax, eax
0x18000397b  js      loc_180003A7C
0x180003981  mov     [rsp+28h+arg_0], rbx
0x180003986  mov     rbx, [rsp+28h+lpMem]
0x18000398b  mov     [rsp+28h+arg_8], rdi
0x180003990  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180003997  nop     word ptr [rax+rax+00000000h]
0x1800039a0  inc     rdi
0x1800039a3  cmp     word ptr [rbx+rdi*2], 0
0x1800039a8  jnz     short loc_1800039A0
0x1800039aa  inc     rdi
0x1800039ad  lea     rcx, [rdi+rdi]; cb
0x1800039b1  call    cs:__imp_CoTaskMemAlloc
0x1800039b7  mov     [rsi], rax
0x1800039ba  mov     rdx, rax
0x1800039bd  test    rax, rax
0x1800039c0  jz      short loc_180003A3F
0x1800039c2  test    rdi, rdi
0x1800039c5  jz      short loc_180003A2E
0x1800039c7  cmp     rdi, 7FFFFFFFh
0x1800039ce  ja      short loc_180003A27
0x1800039d0  mov     ecx, 7FFFFFFEh
0x1800039d5  test    rcx, rcx
0x1800039d8  jz      short loc_1800039F6
0x1800039da  movzx   eax, word ptr [rbx]
0x1800039dd  test    ax, ax
0x1800039e0  jz      short loc_1800039F6
0x1800039e2  mov     [rdx], ax
0x1800039e5  add     rbx, 2
0x1800039e9  add     rdx, 2
0x1800039ed  dec     rcx
0x1800039f0  sub     rdi, 1
0x1800039f4  jnz     short loc_1800039D5
0x1800039f6  test    rdi, rdi
0x1800039f9  lea     rcx, [rdx-2]
0x1800039fd  mov     ebx, 8007007Ah
0x180003a02  cmovnz  rcx, rdx
0x180003a06  xor     eax, eax
0x180003a08  test    rdi, rdi
0x180003a0b  cmovnz  ebx, eax
0x180003a0e  mov     [rcx], ax
0x180003a11  test    ebx, ebx
0x180003a13  jns     short loc_180003A44
0x180003a15  mov     rcx, [rsi]; pv
0x180003a18  call    cs:__imp_CoTaskMemFree
0x180003a1e  mov     qword ptr [rsi], 0
0x180003a25  jmp     short loc_180003A44
0x180003a27  mov     ebx, 80070057h
0x180003a2c  jmp     short loc_180003A38
0x180003a2e  mov     ebx, 80070057h
0x180003a33  test    rdi, rdi
0x180003a36  jz      short loc_180003A11
0x180003a38  xor     eax, eax
0x180003a3a  mov     [rdx], ax
0x180003a3d  jmp     short loc_180003A15
0x180003a3f  mov     ebx, 8007000Eh
0x180003a44  mov     rdi, [rsp+28h+lpMem]
0x180003a49  test    rdi, rdi
0x180003a4c  jz      short loc_180003A70
0x180003a4e  call    cs:__imp_GetProcessHeap
0x180003a54  test    rax, rax
0x180003a57  jz      short loc_180003A70
0x180003a59  mov     r8, rdi; lpMem
0x180003a5c  xor     edx, edx; dwFlags
0x180003a5e  mov     rcx, rax; hHeap
0x180003a61  call    cs:__imp_HeapFree
0x180003a67  test    eax, eax
0x180003a69  jnz     short loc_180003A70
0x180003a6b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180003a70  mov     rdi, [rsp+28h+arg_8]
0x180003a75  mov     eax, ebx
0x180003a77  mov     rbx, [rsp+28h+arg_0]
0x180003a7c  add     rsp, 20h
0x180003a80  pop     rsi
0x180003a81  retn
```
