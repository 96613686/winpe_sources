# GetBasicProfileFolderPathEx

- ea: `0x1800087f0`
- end: `0x18000890a`
- name: `GetBasicProfileFolderPathEx`
- size: `282`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016bec`

## callees

- `0x180005b90`
- `0x1800087f0`
- `0x180008910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000889f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000889f`

## pseudocode

```c
__int64 __fastcall GetBasicProfileFolderPathEx(__int64 a1, __int64 a2, _WORD *a3, unsigned __int64 a4)
{
  int BasicProfileFolderPathAlloc; // esi
  void *v7; // rsi
  __int64 v8; // rax
  _WORD *v9; // rdx
  int v10; // ebp
  HANDLE ProcessHeap; // rax
  LPVOID lpMem[5]; // [rsp+20h] [rbp-28h] BYREF

  lpMem[0] = 0;
  lpMem[1] = (LPVOID)-1LL;
  lpMem[2] = (LPVOID)-1LL;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(a1, a2, lpMem);
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpMem);
    return (unsigned int)BasicProfileFolderPathAlloc;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    goto LABEL_16;
  }
  if ( a4 > 0x7FFFFFFF )
  {
    v10 = -2147024809;
    *a3 = 0;
LABEL_16:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpMem);
    return (unsigned int)v10;
  }
  v7 = lpMem[0];
  v8 = 2147483646;
  v9 = lpMem[0];
  v10 = 0;
  while ( v8 && *v9 )
  {
    *a3++ = *v9++;
    --v8;
    if ( !--a4 )
    {
      --a3;
      v10 = -2147024774;
      break;
    }
  }
  *a3 = 0;
  if ( v10 < 0 )
    goto LABEL_16;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1800087f0  mov     [rsp+arg_8], rbx
0x1800087f5  mov     [rsp+arg_10], rsi
0x1800087fa  push    rdi
0x1800087fb  sub     rsp, 40h
0x1800087ff  mov     rdi, r8
0x180008802  mov     [rsp+48h+lpMem], 0
0x18000880b  lea     r8, [rsp+48h+lpMem]
0x180008810  mov     [rsp+48h+var_20], 0FFFFFFFFFFFFFFFFh
0x180008819  mov     rbx, r9
0x18000881c  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFFh
0x180008825  call    GetBasicProfileFolderPathAlloc
0x18000882a  mov     esi, eax
0x18000882c  test    eax, eax
0x18000882e  js      loc_1800088CA
0x180008834  mov     [rsp+48h+arg_0], rbp
0x180008839  test    rbx, rbx
0x18000883c  jz      loc_1800088ED
0x180008842  cmp     rbx, 7FFFFFFFh
0x180008849  ja      loc_1800088E6
0x18000884f  mov     rsi, [rsp+48h+lpMem]
0x180008854  mov     eax, 7FFFFFFEh
0x180008859  mov     rdx, rsi
0x18000885c  xor     ebp, ebp
0x18000885e  xchg    ax, ax
0x180008860  test    rax, rax
0x180008863  jz      short loc_180008891
0x180008865  movzx   ecx, word ptr [rdx]
0x180008868  test    cx, cx
0x18000886b  jz      short loc_18000888C
0x18000886d  mov     [rdi], cx
0x180008870  add     rdx, 2
0x180008874  add     rdi, 2
0x180008878  dec     rax
0x18000887b  sub     rbx, 1
0x18000887f  jnz     short loc_180008860
0x180008881  sub     rdi, 2
0x180008885  mov     ebp, 8007007Ah
0x18000888a  jmp     short loc_180008891
0x18000888c  test    rbx, rbx
0x18000888f  jz      short loc_180008881
0x180008891  xor     eax, eax
0x180008893  mov     [rdi], ax
0x180008896  test    ebp, ebp
0x180008898  js      short loc_1800088FC
0x18000889a  test    rsi, rsi
0x18000889d  jz      short loc_1800088B3
0x18000889f  call    cs:__imp_GetProcessHeap
0x1800088a5  mov     r8, rsi; lpMem
0x1800088a8  xor     edx, edx; dwFlags
0x1800088aa  mov     rcx, rax; hHeap
0x1800088ad  call    cs:__imp_HeapFree
0x1800088b3  xor     eax, eax
0x1800088b5  mov     rbp, [rsp+48h+arg_0]
0x1800088ba  mov     rbx, [rsp+48h+arg_8]
0x1800088bf  mov     rsi, [rsp+48h+arg_10]
0x1800088c4  add     rsp, 40h
0x1800088c8  pop     rdi
0x1800088c9  retn
0x1800088ca  lea     rcx, [rsp+48h+lpMem]
0x1800088cf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800088d4  mov     rbx, [rsp+48h+arg_8]
0x1800088d9  mov     eax, esi
0x1800088db  mov     rsi, [rsp+48h+arg_10]
0x1800088e0  add     rsp, 40h
0x1800088e4  pop     rdi
0x1800088e5  retn
0x1800088e6  mov     ebp, 80070057h
0x1800088eb  jmp     short loc_1800088F7
0x1800088ed  mov     ebp, 80070057h
0x1800088f2  test    rbx, rbx
0x1800088f5  jz      short loc_1800088FC
0x1800088f7  xor     ecx, ecx
0x1800088f9  mov     [rdi], cx
0x1800088fc  lea     rcx, [rsp+48h+lpMem]
0x180008901  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180008906  mov     eax, ebp
0x180008908  jmp     short loc_1800088B5
```
