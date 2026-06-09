# FastWppTraceMessage

- ea: `0x18002bd74`
- end: `0x18002befd`
- name: `FastWppTraceMessage`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002d008`
- `0x18002d0a8`

## callees

- `0x18002bce8`
- `0x18002bd74`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bedc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bedc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002be57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002be57`
- `ntdll!EtwEventWriteEx` at `0x18002bebf`
- `ntdll!EtwEventWriteEx` at `0x18002bebf`

## pseudocode

```c
int FastWppTraceMessage(__int16 a1, __int16 a2, __int64 a3, ...)
{
  int result; // eax
  void *v4; // rbx
  LPVOID v5; // rax
  __int128 v6; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v7; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v9[256]; // [rsp+80h] [rbp-80h] BYREF
  va_list va; // [rsp+1C8h] [rbp+C8h] BYREF

  va_start(va, a3);
  result = FastWppInitState;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)dwBytes = 0;
  if ( FastWppInitState == 2 )
  {
    LOWORD(v6) = a2;
    BYTE4(v6) = HIBYTE(a1);
    v4 = 0;
    BYTE12(v7) = 4;
    DWORD2(v7) = 16;
    BYTE4(dwBytes[1]) = 0;
    LODWORD(dwBytes[1]) = 256;
    *((_QWORD *)&v6 + 1) = 1LL << a1;
    *(_QWORD *)&v7 = a3;
    dwBytes[0] = (SIZE_T)v9;
    FastWppPackEvent((__int64 *)va, v9, 256, &dwBytes[1]);
    if ( LODWORD(dwBytes[1]) > 0x100 )
    {
      v5 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, LODWORD(dwBytes[1]));
      v4 = v5;
      if ( v5 )
      {
        dwBytes[0] = (SIZE_T)v5;
        FastWppPackEvent((__int64 *)va, v5, LODWORD(dwBytes[1]), &dwBytes[1]);
      }
      else
      {
        LODWORD(dwBytes[1]) = 256;
      }
    }
    result = EtwEventWriteEx(FastWppRegHandle, &v6, 0, 0, 0, 0, 2, &v7, 0);
    if ( v4 )
      return HeapFree(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return result;
}

```

## disassembly

```asm
0x18002bd74  mov     [rsp-8+arg_10], r8
0x18002bd79  mov     [rsp-8+arg_18], r9
0x18002bd7e  push    rbp
0x18002bd7f  push    rbx
0x18002bd80  push    r14
0x18002bd82  lea     rbp, [rsp-90h]
0x18002bd8a  sub     rsp, 190h
0x18002bd91  mov     rax, cs:__security_cookie
0x18002bd98  xor     rax, rsp
0x18002bd9b  mov     [rbp+0A0h+var_20], rax
0x18002bda2  mov     eax, cs:FastWppInitState
0x18002bda8  xorps   xmm1, xmm1
0x18002bdab  mov     [rsp+1A0h+var_160], 0
0x18002bdb4  xorps   xmm0, xmm0
0x18002bdb7  movups  [rsp+1A0h+var_158], xmm0
0x18002bdbc  movups  [rsp+1A0h+var_148], xmm1
0x18002bdc1  movups  xmmword ptr [rsp+1A0h+dwBytes], xmm1
0x18002bdc6  cmp     eax, 2
0x18002bdc9  jnz     loc_18002BEE2
0x18002bdcf  movzx   eax, cx
0x18002bdd2  mov     word ptr [rsp+1A0h+var_158], dx
0x18002bdd7  shr     ax, 8
0x18002bddb  lea     r14, [rbp+0A0h+arg_18]
0x18002bde2  mov     byte ptr [rsp+1A0h+var_158+4], al
0x18002bde6  lea     r9, [rsp+1A0h+dwBytes+8]
0x18002bdeb  xor     ebx, ebx
0x18002bded  mov     byte ptr [rsp+1A0h+var_148+0Ch], 4
0x18002bdf2  mov     r8d, 100h
0x18002bdf8  mov     dword ptr [rsp+1A0h+var_148+8], 10h
0x18002be00  lea     rdx, [rbp+0A0h+var_120]
0x18002be04  mov     byte ptr [rsp+1A0h+dwBytes+0Ch], bl
0x18002be08  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18002be10  lea     eax, [rbx+1]
0x18002be13  shl     rax, cl
0x18002be16  mov     rcx, r14
0x18002be19  mov     qword ptr [rsp+1A0h+var_158+8], rax
0x18002be1e  mov     rax, [rbp+0A0h+arg_10]
0x18002be25  mov     qword ptr [rsp+1A0h+var_148], rax
0x18002be2a  lea     rax, [rbp+0A0h+var_120]
0x18002be2e  mov     [rsp+1A0h+dwBytes], rax
0x18002be33  call    FastWppPackEvent
0x18002be38  cmp     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18002be40  jbe     short loc_18002BE89
0x18002be42  mov     rcx, gs:60h
0x18002be4b  lea     edx, [rbx+8]; dwFlags
0x18002be4e  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]; dwBytes
0x18002be53  mov     rcx, [rcx+30h]; hHeap
0x18002be57  call    cs:__imp_HeapAlloc
0x18002be5d  mov     rbx, rax
0x18002be60  test    rax, rax
0x18002be63  jz      short loc_18002BE81
0x18002be65  mov     r8d, dword ptr [rsp+1A0h+dwBytes+8]
0x18002be6a  lea     r9, [rsp+1A0h+dwBytes+8]
0x18002be6f  mov     rdx, rax
0x18002be72  mov     [rsp+1A0h+dwBytes], rax
0x18002be77  mov     rcx, r14
0x18002be7a  call    FastWppPackEvent
0x18002be7f  jmp     short loc_18002BE89
0x18002be81  mov     dword ptr [rsp+1A0h+dwBytes+8], 100h
0x18002be89  mov     rcx, cs:FastWppRegHandle
0x18002be90  lea     rax, [rsp+1A0h+var_148]
0x18002be95  mov     [rsp+1A0h+var_168], rax
0x18002be9a  lea     rdx, [rsp+1A0h+var_158]
0x18002be9f  mov     [rsp+1A0h+var_170], 2
0x18002bea7  xor     r9d, r9d
0x18002beaa  mov     [rsp+1A0h+var_178], 0
0x18002beb3  xor     r8d, r8d
0x18002beb6  mov     [rsp+1A0h+var_180], 0
0x18002bebf  call    cs:__imp_EtwEventWriteEx
0x18002bec5  test    rbx, rbx
0x18002bec8  jz      short loc_18002BEE2
0x18002beca  mov     rcx, gs:60h
0x18002bed3  mov     r8, rbx; lpMem
0x18002bed6  xor     edx, edx; dwFlags
0x18002bed8  mov     rcx, [rcx+30h]; hHeap
0x18002bedc  call    cs:__imp_HeapFree
0x18002bee2  mov     rcx, [rbp+0A0h+var_20]
0x18002bee9  xor     rcx, rsp; StackCookie
0x18002beec  call    __security_check_cookie
0x18002bef1  add     rsp, 190h
0x18002bef8  pop     r14
0x18002befa  pop     rbx
0x18002befb  pop     rbp
0x18002befc  retn
```
