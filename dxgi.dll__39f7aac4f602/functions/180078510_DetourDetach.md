# DetourDetach

- ea: `0x180078510`
- end: `0x180078684`
- name: `DetourDetach`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180074998`

## callees

- `0x18001b22c`
- `0x180076440`
- `0x180078450`
- `0x180078510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078520`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800785fd`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800785fd`

## pseudocode

```c
__int64 __fastcall DetourDetach(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax
  _DWORD *v5; // rbx
  DWORD LastError; // edi
  __int64 v7; // rdi
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  SIZE_T v10; // rdx
  void *v11; // rbp
  DWORD flOldProtect; // [rsp+40h] [rbp+18h] BYREF

  if ( dword_180108E40 != GetCurrentThreadId() )
    return 4317;
  result = (unsigned int)dword_180108E44;
  if ( !dword_180108E44 )
  {
    if ( !a2 )
      return 87;
    if ( !a1 )
      return 6;
    if ( !*a1 )
    {
      dword_180108E44 = 6;
      qword_180108E48 = (__int64)a1;
      return 6;
    }
    v5 = operator new(0x30u);
    if ( v5 )
    {
      v7 = DetourCodeFromPointer(*a1, 0);
      v8 = DetourCodeFromPointer(a2, 0);
      v9 = *(unsigned __int8 *)(v7 + 62);
      if ( (_BYTE)v9 && (v10 = *(unsigned __int8 *)(v7 + 62), v9 <= 0x1E) && *(_QWORD *)(v7 + 80) == v8 )
      {
        v11 = (void *)(*(_QWORD *)(v7 + 72) - v9);
        flOldProtect = 0;
        if ( VirtualProtect(v11, v10, 0x40u, &flOldProtect) )
        {
          v5[2] = 1;
          *((_QWORD *)v5 + 2) = a1;
          *((_QWORD *)v5 + 4) = v7;
          *((_QWORD *)v5 + 3) = v11;
          v5[10] = flOldProtect;
          *(_QWORD *)v5 = qword_180108E58;
          result = 0;
          qword_180108E58 = v5;
          return result;
        }
        LastError = GetLastError();
      }
      else
      {
        LastError = 9;
        if ( dword_180108E38 )
          goto LABEL_20;
      }
    }
    else
    {
      LastError = 8;
    }
    dword_180108E44 = LastError;
    if ( !v5 )
    {
LABEL_21:
      qword_180108E48 = (__int64)a1;
      return LastError;
    }
LABEL_20:
    operator delete(v5, 0x30u);
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x180078510  mov     [rsp+arg_18], rbp
0x180078515  push    rsi
0x180078516  sub     rsp, 20h
0x18007851a  mov     rbp, rdx
0x18007851d  mov     rsi, rcx
0x180078520  call    cs:__imp_GetCurrentThreadId
0x180078526  cmp     cs:dword_180108E40, eax
0x18007852c  jz      short loc_18007853E
0x18007852e  mov     eax, 10DDh
0x180078533  mov     rbp, [rsp+28h+arg_18]
0x180078538  add     rsp, 20h
0x18007853c  pop     rsi
0x18007853d  retn
0x18007853e  mov     eax, cs:dword_180108E44
0x180078544  test    eax, eax
0x180078546  jnz     loc_180078679
0x18007854c  test    rbp, rbp
0x18007854f  jnz     short loc_180078561
0x180078551  mov     eax, 57h ; 'W'
0x180078556  mov     rbp, [rsp+28h+arg_18]
0x18007855b  add     rsp, 20h
0x18007855f  pop     rsi
0x180078560  retn
0x180078561  test    rsi, rsi
0x180078564  jz      short loc_18007857D
0x180078566  cmp     qword ptr [rsi], 0
0x18007856a  jnz     short loc_18007858D
0x18007856c  mov     cs:dword_180108E44, 6
0x180078576  mov     cs:qword_180108E48, rsi
0x18007857d  mov     eax, 6
0x180078582  mov     rbp, [rsp+28h+arg_18]
0x180078587  add     rsp, 20h
0x18007858b  pop     rsi
0x18007858c  retn
0x18007858d  mov     [rsp+28h+arg_0], rbx
0x180078592  mov     ecx, 30h ; '0'; dwBytes
0x180078597  mov     [rsp+28h+arg_8], rdi
0x18007859c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800785a1  mov     rbx, rax
0x1800785a4  test    rax, rax
0x1800785a7  jnz     short loc_1800785B3
0x1800785a9  mov     edi, 8
0x1800785ae  jmp     loc_18007864E
0x1800785b3  mov     rcx, [rsi]
0x1800785b6  xor     edx, edx
0x1800785b8  call    DetourCodeFromPointer
0x1800785bd  xor     edx, edx
0x1800785bf  mov     rcx, rbp
0x1800785c2  mov     rdi, rax
0x1800785c5  call    DetourCodeFromPointer
0x1800785ca  movzx   ecx, byte ptr [rdi+3Eh]
0x1800785ce  test    cl, cl
0x1800785d0  jz      short loc_180078640
0x1800785d2  mov     edx, ecx; dwSize
0x1800785d4  cmp     rcx, 1Eh
0x1800785d8  ja      short loc_180078640
0x1800785da  cmp     [rdi+50h], rax
0x1800785de  jnz     short loc_180078640
0x1800785e0  mov     rbp, [rdi+48h]
0x1800785e4  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800785e9  sub     rbp, rcx
0x1800785ec  mov     [rsp+28h+flOldProtect], 0
0x1800785f4  mov     rcx, rbp; lpAddress
0x1800785f7  mov     r8d, 40h ; '@'; flNewProtect
0x1800785fd  call    cs:__imp_VirtualProtect
0x180078603  test    eax, eax
0x180078605  jnz     short loc_180078611
0x180078607  call    cs:__imp_GetLastError
0x18007860d  mov     edi, eax
0x18007860f  jmp     short loc_18007864E
0x180078611  mov     dword ptr [rbx+8], 1
0x180078618  mov     [rbx+10h], rsi
0x18007861c  mov     [rbx+20h], rdi
0x180078620  mov     [rbx+18h], rbp
0x180078624  mov     eax, [rsp+28h+flOldProtect]
0x180078628  mov     [rbx+28h], eax
0x18007862b  mov     rax, cs:qword_180108E58
0x180078632  mov     [rbx], rax
0x180078635  xor     eax, eax
0x180078637  mov     cs:qword_180108E58, rbx
0x18007863e  jmp     short loc_18007866F
0x180078640  cmp     cs:dword_180108E38, 0
0x180078647  mov     edi, 9
0x18007864c  jnz     short loc_180078659
0x18007864e  mov     cs:dword_180108E44, edi
0x180078654  test    rbx, rbx
0x180078657  jz      short loc_180078666
0x180078659  mov     edx, 30h ; '0'; unsigned __int64
0x18007865e  mov     rcx, rbx; void *
0x180078661  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078666  mov     cs:qword_180108E48, rsi
0x18007866d  mov     eax, edi
0x18007866f  mov     rbx, [rsp+28h+arg_0]
0x180078674  mov     rdi, [rsp+28h+arg_8]
0x180078679  mov     rbp, [rsp+28h+arg_18]
0x18007867e  add     rsp, 20h
0x180078682  pop     rsi
0x180078683  retn
```
