# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x1800081f0`
- end: `0x1800082d2`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `226`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b0a0`

## callees

- `0x1800081f0`
- `0x18000c114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000828f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000828f`
- `USER32!UnregisterClassA` at `0x180008258`
- `USER32!UnregisterClassA` at `0x180008258`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  __int64 result; // rax
  int *v5; // rdi
  int v6; // ebp
  void *v7; // rcx

  if ( !a1 )
    return 2147942487LL;
  result = *(unsigned int *)a1;
  if ( !(_DWORD)result )
    return result;
  if ( (_DWORD)result != 72 )
    return 2147942487LL;
  v5 = (int *)((char *)a1 + 64);
  v6 = 0;
  if ( *((int *)a1 + 16) > 0 )
  {
    do
    {
      if ( v6 < 0 || v6 >= *((_DWORD *)a1 + 16) )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        __debugbreak();
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)a1 + 7) + 2LL * v6++), a2);
    }
    while ( v6 < *v5 );
    v5 = (int *)((char *)a1 + 64);
  }
  v7 = (void *)*((_QWORD *)a1 + 7);
  if ( v7 )
  {
    if ( *((int *)a1 + 16) > 0 )
      v5 = (int *)((char *)a1 + 64);
    free(v7);
    *((_QWORD *)a1 + 7) = 0;
  }
  *v5 = 0;
  *((_DWORD *)a1 + 17) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
  result = 0;
  *(_DWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800081f0  mov     [rsp+arg_18], rbx
0x1800081f5  push    rsi
0x1800081f6  sub     rsp, 20h
0x1800081fa  mov     rsi, rdx
0x1800081fd  mov     rbx, rcx
0x180008200  test    rcx, rcx
0x180008203  jz      loc_1800082CB
0x180008209  mov     eax, [rcx]
0x18000820b  test    eax, eax
0x18000820d  jnz     short loc_18000821A
0x18000820f  mov     rbx, [rsp+28h+arg_18]
0x180008214  add     rsp, 20h
0x180008218  pop     rsi
0x180008219  retn
0x18000821a  cmp     eax, 48h ; 'H'
0x18000821d  jnz     loc_1800082CB
0x180008223  mov     [rsp+28h+arg_0], rbp
0x180008228  mov     [rsp+28h+arg_8], rdi
0x18000822d  lea     rdi, [rcx+40h]
0x180008231  mov     [rsp+28h+arg_10], r14
0x180008236  xor     r14d, r14d
0x180008239  mov     ebp, r14d
0x18000823c  cmp     [rdi], r14d
0x18000823f  jle     short loc_180008268
0x180008241  test    ebp, ebp
0x180008243  js      short loc_1800082B4
0x180008245  cmp     ebp, [rbx+40h]
0x180008248  jge     short loc_1800082B4
0x18000824a  mov     rax, [rbx+38h]
0x18000824e  mov     rdx, rsi; hInstance
0x180008251  movsxd  rcx, ebp
0x180008254  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180008258  call    cs:__imp_UnregisterClassA
0x18000825e  inc     ebp
0x180008260  cmp     ebp, [rdi]
0x180008262  jl      short loc_180008241
0x180008264  lea     rdi, [rbx+40h]
0x180008268  mov     rcx, [rbx+38h]; Block
0x18000826c  test    rcx, rcx
0x18000826f  jz      short loc_180008284
0x180008271  cmp     [rbx+40h], r14d
0x180008275  jle     short loc_18000827B
0x180008277  lea     rdi, [rbx+40h]
0x18000827b  call    free
0x180008280  mov     [rbx+38h], r14
0x180008284  lea     rcx, [rbx+8]; lpCriticalSection
0x180008288  mov     [rdi], r14d
0x18000828b  mov     [rbx+44h], r14d
0x18000828f  call    cs:__imp_DeleteCriticalSection
0x180008295  mov     rdi, [rsp+28h+arg_8]
0x18000829a  xor     eax, eax
0x18000829c  mov     rbp, [rsp+28h+arg_0]
0x1800082a1  mov     [rbx], r14d
0x1800082a4  mov     r14, [rsp+28h+arg_10]
0x1800082a9  mov     rbx, [rsp+28h+arg_18]
0x1800082ae  add     rsp, 20h
0x1800082b2  pop     rsi
0x1800082b3  retn
0x1800082b4  xor     r9d, r9d; lpArguments
0x1800082b7  xor     r8d, r8d; nNumberOfArguments
0x1800082ba  mov     edx, 1; dwExceptionFlags
0x1800082bf  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800082c4  call    cs:__imp_RaiseException
0x1800082ca  int     3; Trap to Debugger
0x1800082cb  mov     eax, 80070057h
0x1800082d0  jmp     short loc_1800082A9
```
