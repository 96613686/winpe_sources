# PerflibciCreateOrFindCounterSet

- ea: `0x180002dd0`
- end: `0x18000307d`
- name: `PerflibciCreateOrFindCounterSet`
- size: `685`
- prototype: `__int64 __usercall@<rax>(void *Buf1@<rcx>, void *, __int16, int)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x180001520`
- `0x180002810`
- `0x1800044a0`
- `0x180005f20`
- `0x18000cc70`
- `0x1800146c8`
- `0x180015cf4`

## callees

- `0x180002dd0`
- `0x180005da0`
- `0x1800071b0`
- `0x180007300`
- `0x18001e425`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002f00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003048`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003048`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003068`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003052`

## pseudocode

```c
char *__fastcall PerflibciCreateOrFindCounterSet(
        __int128 *Buf1,
        _DWORD *a2,
        unsigned int a3,
        unsigned int a4,
        void *a5,
        unsigned __int16 a6,
        int a7)
{
  char *v7; // rbx
  __int64 v8; // r15
  DWORD v10; // esi
  struct PERFLIBCI_RED_BLACK_NODE *v11; // rbx
  int v12; // edi
  struct PERFLIBCI_RED_BLACK_NODE *v13; // r14
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r15
  char v18; // r9
  unsigned int v19; // edx
  int v20; // r8d
  __int128 v21; // xmm0
  void *v22; // rcx
  char *v23; // rcx
  size_t Size; // [rsp+60h] [rbp+8h]

  v7 = 0;
  v8 = a3;
  if ( !Buf1 || a7 && (!a2 || !a3) )
    goto LABEL_41;
  Size = a3;
  if ( a3 != 56LL * a4 )
    goto LABEL_41;
  v10 = PerflibciLocalWaitForMutex(g_hGlobalMutex);
  if ( v10 )
  {
LABEL_42:
    SetLastError(v10);
    return v7;
  }
  v11 = qword_18002BEA0;
  v12 = 0;
  v13 = 0;
  if ( !qword_18002BEA0 )
  {
LABEL_17:
    if ( a7 && !v10 )
    {
      if ( (unsigned int)v8 < (unsigned int)v8 + a6 + 200 )
      {
        v16 = operator new(a6 + v8 + 200);
        v17 = v16;
        if ( v16 )
        {
          v7 = (char *)(v16 + 48);
          InitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 88));
          v18 = 1;
          v19 = 0;
          v20 = 200;
          *(_QWORD *)(v17 + 24) = g_ObjectList;
          *(_QWORD *)(v17 + 32) = v7;
          g_ObjectList = (void *)v17;
          *(_QWORD *)(v17 + 16) = v13;
          *(_DWORD *)(v17 + 40) = 1;
          while ( v19 < a4 )
          {
            if ( a2[14 * v19 + 4] < 0xC8u )
            {
              v18 = 0;
              break;
            }
            ++v19;
          }
          v21 = *Buf1;
          v22 = v7 + 152;
          *((_QWORD *)v7 + 2) = 0;
          *((_QWORD *)v7 + 10) = 0;
          if ( !v18 )
            v20 = 100;
          *((_QWORD *)v7 + 11) = 0;
          *((_DWORD *)v7 + 33) = v20;
          *((_DWORD *)v7 + 24) = 0;
          *(_OWORD *)(v7 + 24) = v21;
          *((_QWORD *)v7 + 17) = 0;
          *((_DWORD *)v7 + 32) = a4;
          *((_QWORD *)v7 + 15) = v22;
          memcpy_0(v22, a2, Size);
          v23 = &v7[Size + 152];
          *((_WORD *)v7 + 52) = a6;
          *((_QWORD *)v7 + 14) = v23;
          *((_WORD *)v7 + 53) = a6;
          memcpy_0(v23, a5, a6);
          v7[144] = 1;
          if ( v13 )
          {
            if ( v12 >= 0 )
              *((_QWORD *)v13 + 1) = v17;
            else
              *(_QWORD *)v13 = v17;
          }
          else
          {
            qword_18002BEA0 = (struct PERFLIBCI_RED_BLACK_NODE *)v17;
          }
          PerflibciInsertRedBlackNode(&qword_18002BEA0, (struct PERFLIBCI_RED_BLACK_NODE *)v17);
          *((_DWORD *)qword_18002BEA0 + 10) = 0;
          goto LABEL_36;
        }
      }
      v10 = 14;
    }
    v7 = 0;
    goto LABEL_36;
  }
  while ( 1 )
  {
    v14 = *((_QWORD *)v11 + 4);
    if ( !v14 )
    {
      v10 = 13;
      goto LABEL_17;
    }
    v15 = memcmp_0(Buf1, (const void *)(v14 + 24), 0x10u);
    v12 = v15;
    if ( !v15 )
      break;
    v13 = v11;
    if ( v15 >= 0 )
      v11 = (struct PERFLIBCI_RED_BLACK_NODE *)((char *)v11 + 8);
    v11 = *(struct PERFLIBCI_RED_BLACK_NODE **)v11;
    if ( !v11 )
      goto LABEL_17;
  }
  v7 = (char *)v11 + 48;
  if ( v7 )
    v7[144] = 1;
LABEL_36:
  if ( g_hGlobalMutex && !ReleaseMutex(g_hGlobalMutex) )
    GetLastError();
  if ( !v7 )
  {
    if ( !v10 )
    {
LABEL_41:
      v10 = 87;
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  return v7;
}

```

## disassembly

```asm
0x180002dd0  mov     [rsp+arg_18], r9d
0x180002dd5  mov     [rsp+Src], rdx
0x180002dda  push    rbx
0x180002ddb  push    rbp
0x180002ddc  push    rsi
0x180002ddd  push    r12
0x180002ddf  push    r15
0x180002de1  sub     rsp, 30h
0x180002de5  xor     ebx, ebx
0x180002de7  mov     r15d, r8d
0x180002dea  mov     rbp, rcx
0x180002ded  test    rcx, rcx
0x180002df0  jz      loc_180003061
0x180002df6  mov     r12d, [rsp+58h+arg_30]
0x180002dfe  test    r12d, r12d
0x180002e01  jz      short loc_180002E15
0x180002e03  test    rdx, rdx
0x180002e06  jz      loc_180003061
0x180002e0c  test    r8d, r8d
0x180002e0f  jz      loc_180003061
0x180002e15  mov     eax, r9d
0x180002e18  imul    rcx, rax, 38h ; '8'
0x180002e1c  mov     [rsp+58h+Size], r15
0x180002e21  cmp     r15, rcx
0x180002e24  jnz     loc_180003061
0x180002e2a  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180002e31  call    ?PerflibciLocalWaitForMutex@@YAKPEAX@Z; PerflibciLocalWaitForMutex(void *)
0x180002e36  mov     esi, eax
0x180002e38  test    eax, eax
0x180002e3a  jnz     loc_180003066
0x180002e40  mov     rbx, cs:qword_18002BEA0
0x180002e47  mov     [rsp+58h+arg_10], rdi
0x180002e4c  xor     edi, edi
0x180002e4e  mov     [rsp+58h+var_38], r14
0x180002e53  xor     r14d, r14d
0x180002e56  mov     [rsp+58h+var_30], r13
0x180002e5b  test    rbx, rbx
0x180002e5e  jz      short loc_180002EAF
0x180002e60  mov     rdx, [rbx+20h]
0x180002e64  test    rdx, rdx
0x180002e67  jz      short loc_180002EAA
0x180002e69  add     rdx, 18h; Buf2
0x180002e6d  mov     r8d, 10h; Size
0x180002e73  mov     rcx, rbp; Buf1
0x180002e76  call    memcmp_0
0x180002e7b  mov     edi, eax
0x180002e7d  test    eax, eax
0x180002e7f  jz      short loc_180002E94
0x180002e81  mov     r14, rbx
0x180002e84  js      short loc_180002E8A
0x180002e86  add     rbx, 8
0x180002e8a  mov     rbx, [rbx]
0x180002e8d  test    rbx, rbx
0x180002e90  jnz     short loc_180002E60
0x180002e92  jmp     short loc_180002EAF
0x180002e94  add     rbx, 30h ; '0'
0x180002e98  jz      loc_18000302D
0x180002e9e  mov     byte ptr [rbx+90h], 1
0x180002ea5  jmp     loc_18000302D
0x180002eaa  mov     esi, 0Dh
0x180002eaf  test    r12d, r12d
0x180002eb2  jz      loc_18000302B
0x180002eb8  test    esi, esi
0x180002eba  jnz     loc_18000302B
0x180002ec0  movzx   r12d, [rsp+58h+arg_28]
0x180002ec9  lea     ecx, [r12+0C8h]
0x180002ed1  add     ecx, r15d
0x180002ed4  cmp     r15d, ecx
0x180002ed7  jnb     loc_180003026
0x180002edd  lea     rcx, [r15+0C8h]
0x180002ee4  add     rcx, r12
0x180002ee7  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180002eec  mov     r15, rax
0x180002eef  test    rax, rax
0x180002ef2  jz      loc_180003026
0x180002ef8  lea     rbx, [rax+30h]
0x180002efc  lea     rcx, [rbx+28h]; lpCriticalSection
0x180002f00  call    cs:__imp_InitializeCriticalSection
0x180002f06  mov     rax, cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180002f0d  mov     r9b, 1
0x180002f10  mov     r10, [rsp+58h+Src]
0x180002f15  xor     edx, edx
0x180002f17  mov     r11d, [rsp+58h+arg_18]
0x180002f1c  mov     r8d, 0C8h
0x180002f22  mov     [r15+18h], rax
0x180002f26  mov     [r15+20h], rbx
0x180002f2a  mov     cs:?g_ObjectList@@3PEAUPERFLIBCI_RED_BLACK_NODE@@EA, r15; PERFLIBCI_RED_BLACK_NODE * g_ObjectList
0x180002f31  mov     [r15+10h], r14
0x180002f35  mov     dword ptr [r15+28h], 1
0x180002f3d  cmp     edx, r11d
0x180002f40  jnb     short loc_180002F56
0x180002f42  mov     eax, edx
0x180002f44  imul    rcx, rax, 38h ; '8'
0x180002f48  cmp     [rcx+r10+10h], r8d
0x180002f4d  jb      short loc_180002F53
0x180002f4f  inc     edx
0x180002f51  jmp     short loc_180002F3D
0x180002f53  xor     r9b, r9b
0x180002f56  movups  xmm0, xmmword ptr [rbp+0]
0x180002f5a  mov     rbp, [rsp+58h+Size]
0x180002f5f  lea     rcx, [rbx+98h]; void *
0x180002f66  test    r9b, r9b
0x180002f69  mov     qword ptr [rbx+10h], 0
0x180002f71  mov     eax, 64h ; 'd'
0x180002f76  mov     qword ptr [rbx+50h], 0
0x180002f7e  cmovz   r8d, eax
0x180002f82  mov     qword ptr [rbx+58h], 0
0x180002f8a  mov     [rbx+84h], r8d
0x180002f91  mov     rdx, r10; Src
0x180002f94  mov     r8, rbp; Size
0x180002f97  mov     dword ptr [rbx+60h], 0
0x180002f9e  movups  xmmword ptr [rbx+18h], xmm0
0x180002fa2  mov     qword ptr [rbx+88h], 0
0x180002fad  mov     [rbx+80h], r11d
0x180002fb4  mov     [rbx+78h], rcx
0x180002fb8  call    memcpy_0
0x180002fbd  mov     rdx, [rsp+58h+arg_20]; Src
0x180002fc5  lea     rcx, [rbp+98h]
0x180002fcc  add     rcx, rbx; void *
0x180002fcf  mov     [rbx+68h], r12w
0x180002fd4  mov     r8, r12; Size
0x180002fd7  mov     [rbx+70h], rcx
0x180002fdb  mov     [rbx+6Ah], r12w
0x180002fe0  call    memcpy_0
0x180002fe5  mov     byte ptr [rbx+90h], 1
0x180002fec  test    r14, r14
0x180002fef  jz      short loc_180003000
0x180002ff1  test    edi, edi
0x180002ff3  jns     short loc_180002FFA
0x180002ff5  mov     [r14], r15
0x180002ff8  jmp     short loc_180003007
0x180002ffa  mov     [r14+8], r15
0x180002ffe  jmp     short loc_180003007
0x180003000  mov     cs:qword_18002BEA0, r15
0x180003007  mov     rdx, r15; struct PERFLIBCI_RED_BLACK_NODE *
0x18000300a  lea     rcx, qword_18002BEA0; struct PERFLIBCI_RED_BLACK_NODE **
0x180003011  call    ?PerflibciInsertRedBlackNode@@YAXPEAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAU1@@Z; PerflibciInsertRedBlackNode(PERFLIBCI_RED_BLACK_NODE * *,PERFLIBCI_RED_BLACK_NODE *)
0x180003016  mov     rax, cs:qword_18002BEA0
0x18000301d  mov     dword ptr [rax+28h], 0
0x180003024  jmp     short loc_18000302D
0x180003026  mov     esi, 0Eh
0x18000302b  xor     ebx, ebx
0x18000302d  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hMutex
0x180003034  mov     r14, [rsp+58h+var_38]
0x180003039  mov     r13, [rsp+58h+var_30]
0x18000303e  mov     rdi, [rsp+58h+arg_10]
0x180003043  test    rcx, rcx
0x180003046  jz      short loc_180003058
0x180003048  call    cs:__imp_ReleaseMutex
0x18000304e  test    eax, eax
0x180003050  jnz     short loc_180003058
0x180003052  call    cs:__imp_GetLastError
0x180003058  test    rbx, rbx
0x18000305b  jnz     short loc_18000306E
0x18000305d  test    esi, esi
0x18000305f  jnz     short loc_180003066
0x180003061  mov     esi, 57h ; 'W'
0x180003066  mov     ecx, esi; dwErrCode
0x180003068  call    cs:__imp_SetLastError
0x18000306e  mov     rax, rbx
0x180003071  add     rsp, 30h
0x180003075  pop     r15
0x180003077  pop     r12
0x180003079  pop     rsi
0x18000307a  pop     rbp
0x18000307b  pop     rbx
0x18000307c  retn
```
