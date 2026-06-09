# GetCueBannerHelper(ulong,ulong,HWND__ *,uint,ushort * *)

- ea: `0x18002b404`
- end: `0x18002b54a`
- name: `?GetCueBannerHelper@@YAJKKPEAUHWND__@@IPEAPEAG@Z`
- size: `326`
- prototype: `int(unsigned int, unsigned int, HWND, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800291b0`
- `0x18002bf90`

## callees

- `0x180006c58`
- `0x18000771c`
- `0x18000b890`
- `0x18001e4c0`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002b4e5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002b4e5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4f4`

## pseudocode

```c
__int64 __fastcall GetCueBannerHelper(int a1, int a2, HWND a3, unsigned int a4, unsigned __int16 **a5)
{
  int v9; // ebx
  void *v10; // rdi
  unsigned __int16 *v11; // rax
  HANDLE hProcess; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  Buffer[0] = 0;
  hProcess = 0;
  *a5 = 0;
  v9 = 0;
  v10 = SharedAlloc(0x208u, a3, &hProcess);
  if ( !v10 )
    goto LABEL_14;
  v15 = 0;
  v14[0] = a1;
  v14[1] = a2;
  v9 = SendMessageTimeoutHelper((struct OLEACC_TIMEOUTDATA *)v14, a3, a4, (unsigned __int64)v10, 260, &v15);
  if ( v9 < 0 )
  {
    SharedFree(v10, hProcess);
    return (unsigned int)v9;
  }
  if ( v15 )
  {
    if ( ReadProcessMemory(hProcess, v10, Buffer, 0x208u, 0) )
    {
      v11 = SysAllocString(Buffer);
      *a5 = v11;
      if ( !v11 )
        v9 = -2147024882;
    }
  }
  SharedFree(v10, hProcess);
  if ( v9 >= 0 )
  {
LABEL_14:
    if ( !*a5 )
      return 1;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b404  push    rbp
0x18002b406  push    rbx
0x18002b407  push    rsi
0x18002b408  push    rdi
0x18002b409  push    r12
0x18002b40b  push    r13
0x18002b40d  push    r14
0x18002b40f  push    r15
0x18002b411  lea     rbp, [rsp-178h]
0x18002b419  sub     rsp, 278h
0x18002b420  mov     rax, cs:__security_cookie
0x18002b427  xor     rax, rsp
0x18002b42a  mov     [rbp+1B0h+var_50], rax
0x18002b431  mov     rsi, [rbp+1B0h+arg_20]
0x18002b438  mov     r14, r8
0x18002b43b  xor     eax, eax
0x18002b43d  lea     r8, [rsp+2B0h+hProcess]; void **
0x18002b442  mov     r12d, edx
0x18002b445  mov     [rsp+2B0h+Buffer], ax
0x18002b44a  mov     r15d, ecx
0x18002b44d  mov     [rsp+2B0h+hProcess], rax
0x18002b452  mov     rdx, r14; HWND
0x18002b455  mov     qword ptr [rsi], 0
0x18002b45c  mov     ecx, 208h; dwSize
0x18002b461  mov     r13d, r9d
0x18002b464  xor     ebx, ebx
0x18002b466  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002b46b  mov     rdi, rax
0x18002b46e  test    rax, rax
0x18002b471  jz      loc_18002B519
0x18002b477  lea     rax, [rsp+2B0h+var_270]
0x18002b47c  mov     [rsp+2B0h+var_270], rbx
0x18002b481  mov     [rsp+2B0h+var_288], rax; __int64 *
0x18002b486  lea     rcx, [rsp+2B0h+var_278]; struct OLEACC_TIMEOUTDATA *
0x18002b48b  mov     r9, rdi; unsigned __int64
0x18002b48e  mov     [rsp+2B0h+lpNumberOfBytesRead], 104h; __int64
0x18002b497  mov     r8d, r13d; unsigned int
0x18002b49a  mov     [rsp+2B0h+var_278], r15d
0x18002b49f  mov     rdx, r14; HWND
0x18002b4a2  mov     [rsp+2B0h+var_274], r12d
0x18002b4a7  call    ?SendMessageTimeoutHelper@@YAJPEAUOLEACC_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; SendMessageTimeoutHelper(OLEACC_TIMEOUTDATA *,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002b4ac  mov     ebx, eax
0x18002b4ae  test    eax, eax
0x18002b4b0  jns     short loc_18002B4C1
0x18002b4b2  mov     rdx, [rsp+2B0h+hProcess]; hProcess
0x18002b4b7  mov     rcx, rdi; lpAddress
0x18002b4ba  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002b4bf  jmp     short loc_18002B525
0x18002b4c1  cmp     [rsp+2B0h+var_270], 0
0x18002b4c7  jz      short loc_18002B508
0x18002b4c9  mov     rcx, [rsp+2B0h+hProcess]; hProcess
0x18002b4ce  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
0x18002b4d3  mov     r9d, 208h; nSize
0x18002b4d9  mov     [rsp+2B0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18002b4e2  mov     rdx, rdi; lpBaseAddress
0x18002b4e5  call    cs:__imp_ReadProcessMemory
0x18002b4eb  test    eax, eax
0x18002b4ed  jz      short loc_18002B508
0x18002b4ef  lea     rcx, [rsp+2B0h+Buffer]; psz
0x18002b4f4  call    cs:__imp_SysAllocString
0x18002b4fa  test    rax, rax
0x18002b4fd  mov     [rsi], rax
0x18002b500  mov     ecx, 8007000Eh
0x18002b505  cmovz   ebx, ecx
0x18002b508  mov     rdx, [rsp+2B0h+hProcess]; hProcess
0x18002b50d  mov     rcx, rdi; lpAddress
0x18002b510  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002b515  test    ebx, ebx
0x18002b517  js      short loc_18002B525
0x18002b519  cmp     qword ptr [rsi], 0
0x18002b51d  mov     eax, 1
0x18002b522  cmovz   ebx, eax
0x18002b525  mov     eax, ebx
0x18002b527  mov     rcx, [rbp+1B0h+var_50]
0x18002b52e  xor     rcx, rsp; StackCookie
0x18002b531  call    __security_check_cookie
0x18002b536  add     rsp, 278h
0x18002b53d  pop     r15
0x18002b53f  pop     r14
0x18002b541  pop     r13
0x18002b543  pop     r12
0x18002b545  pop     rdi
0x18002b546  pop     rsi
0x18002b547  pop     rbx
0x18002b548  pop     rbp
0x18002b549  retn
```
