# ResourceStringCoAllocFormatMessageVA

- ea: `0x180022020`
- end: `0x18002211d`
- name: `ResourceStringCoAllocFormatMessageVA`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021ff4`

## callees

- `0x180012408`
- `0x180021dfc`
- `0x180021ed8`
- `0x180022020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800220b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002208e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002208e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022102`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800220ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022102`

## pseudocode

```c
__int64 ResourceStringCoAllocFormatMessageVA(int a1, int a2, unsigned __int16 **a3, ...)
{
  int ErrorError; // ebx
  __int64 v5; // rax
  __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  LPWSTR lpBuffer; // [rsp+20h] [rbp-48h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-28h] BYREF
  LPCVOID lpSource[4]; // [rsp+48h] [rbp-20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  lpSource[0] = 0;
  ErrorError = TResourceStringAllocCopyEx<unsigned short *>(
                 a1,
                 a2,
                 (int)a3,
                 (int)ResourceStringAllocCopyExLocalAlloc,
                 lpBuffer,
                 lpSource);
  if ( ErrorError >= 0 )
  {
    *(_QWORD *)Buffer = 0;
    if ( FormatMessageW(0x500u, lpSource[0], 0, 0, Buffer, 0, (va_list *)va) )
    {
      ErrorError = -2147024882;
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v5) );
      v6 = (unsigned int)(v5 + 1);
      v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
      v8 = v7;
      if ( v7 )
      {
        ErrorError = StringCchCopyW(v7, (unsigned int)v6, *(const unsigned __int16 **)Buffer);
        if ( ErrorError >= 0 )
        {
          *a3 = v8;
          v8 = 0;
        }
        CoTaskMemFree(v8);
      }
      LocalFree(*(HLOCAL *)Buffer);
    }
    else
    {
      ErrorError = HRESULTFromLastErrorError();
    }
    LocalFree((HLOCAL)lpSource[0]);
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x180022020  mov     r11, rsp
0x180022023  mov     [r11+8], rbx
0x180022027  mov     [r11+10h], rbp
0x18002202b  mov     [r11+20h], r9
0x18002202f  push    rsi
0x180022030  push    rdi
0x180022031  push    r14
0x180022033  sub     rsp, 50h
0x180022037  lea     rax, [r11-20h]
0x18002203b  xor     ebp, ebp
0x18002203d  lea     r9, _ResourceStringAllocCopyExLocalAlloc; int
0x180022044  mov     [r11-20h], rbp
0x180022048  mov     [r11-40h], rax
0x18002204c  mov     r14, r8
0x18002204f  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180022054  mov     ebx, eax
0x180022056  test    eax, eax
0x180022058  js      loc_180022108
0x18002205e  mov     rdx, [rsp+68h+lpSource]; lpSource
0x180022063  lea     rax, [rsp+68h+arg_18]
0x18002206b  mov     [rsp+68h+Arguments], rax; Arguments
0x180022070  xor     r9d, r9d; dwLanguageId
0x180022073  lea     rax, [rsp+68h+Buffer]
0x180022078  mov     [rsp+68h+nSize], ebp; nSize
0x18002207c  xor     r8d, r8d; dwMessageId
0x18002207f  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180022084  mov     ecx, 500h; dwFlags
0x180022089  mov     qword ptr [rsp+68h+Buffer], rbp
0x18002208e  call    cs:__imp_FormatMessageW
0x180022094  test    eax, eax
0x180022096  jz      short loc_1800220F6
0x180022098  mov     rcx, qword ptr [rsp+68h+Buffer]
0x18002209d  mov     ebx, 8007000Eh
0x1800220a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800220a6  inc     rax
0x1800220a9  cmp     [rcx+rax*2], bp
0x1800220ad  jnz     short loc_1800220A6
0x1800220af  inc     eax
0x1800220b1  mov     esi, eax
0x1800220b3  lea     rcx, [rax+rax]; cb
0x1800220b7  call    cs:__imp_CoTaskMemAlloc
0x1800220bd  mov     rdi, rax
0x1800220c0  test    rax, rax
0x1800220c3  jz      short loc_1800220E9
0x1800220c5  mov     r8, qword ptr [rsp+68h+Buffer]; unsigned __int16 *
0x1800220ca  mov     edx, esi; unsigned __int64
0x1800220cc  mov     rcx, rax; unsigned __int16 *
0x1800220cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800220d4  mov     ebx, eax
0x1800220d6  test    eax, eax
0x1800220d8  js      short loc_1800220E0
0x1800220da  mov     [r14], rdi
0x1800220dd  mov     rdi, rbp
0x1800220e0  mov     rcx, rdi; pv
0x1800220e3  call    cs:__imp_CoTaskMemFree
0x1800220e9  mov     rcx, qword ptr [rsp+68h+Buffer]; hMem
0x1800220ee  call    cs:__imp_LocalFree
0x1800220f4  jmp     short loc_1800220FD
0x1800220f6  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x1800220fb  mov     ebx, eax
0x1800220fd  mov     rcx, [rsp+68h+lpSource]; hMem
0x180022102  call    cs:__imp_LocalFree
0x180022108  mov     rbp, [rsp+68h+arg_8]
0x18002210d  mov     eax, ebx
0x18002210f  mov     rbx, [rsp+68h+arg_0]
0x180022114  add     rsp, 50h
0x180022118  pop     r14
0x18002211a  pop     rdi
0x18002211b  pop     rsi
0x18002211c  retn
```
