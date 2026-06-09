# CAudioTimeCompression::Start(void)

- ea: `0x18004fbb0`
- end: `0x18004fd1d`
- name: `?Start@CAudioTimeCompression@@IEAAJXZ`
- size: `365`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004f4c0`
- `0x18004fae0`

## callees

- `0x180001360`
- `0x180001b80`
- `0x18004fbb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fcaf`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x18004fcaf`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004fbec`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004fc1f`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004fbec`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x18004fc1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fbcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fbcb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioTimeCompression::Start(CAudioTimeCompression *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // rdi
  void *v4; // rcx
  _QWORD *v5; // rdi
  void *v6; // rcx
  int *v7; // rax
  int *v8; // rdi
  int v9; // ecx
  unsigned int v10; // edi
  void *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  v3 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    v4 = (void *)v3[3];
    if ( v4 )
    {
      _aligned_free(v4);
      v3[3] = 0;
    }
    operator delete(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = (_QWORD *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    v6 = (void *)v5[3];
    if ( v6 )
    {
      _aligned_free(v6);
      v5[3] = 0;
    }
    operator delete(v5);
    *((_QWORD *)this + 11) = 0;
  }
  *((_DWORD *)this + 19) = *((_DWORD *)this + 13) - *((_DWORD *)this + 14);
  *((_DWORD *)this + 18) = *((_DWORD *)this + 13) + *((_DWORD *)this + 17) + 2 * *((_DWORD *)this + 16);
  v7 = (int *)operator new(0x20u);
  v8 = v7;
  if ( !v7 )
  {
    *((_QWORD *)this + 10) = 0;
    goto LABEL_19;
  }
  v9 = *((unsigned __int16 *)this + 8);
  *(_QWORD *)v7 = 0;
  v7[2] = 0;
  v7[3] = v9;
  v7[4] = 12288 * v9;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)this + 10) = v7;
  if ( *((_QWORD *)v7 + 3) )
  {
    v10 = -2147418113;
    goto LABEL_20;
  }
  v11 = _aligned_malloc(v7[4], 0x10u);
  *((_QWORD *)v8 + 3) = v11;
  if ( !v11 )
  {
LABEL_19:
    v10 = -2147024882;
    goto LABEL_20;
  }
  v10 = 0;
  *((_BYTE *)this + 22) = 1;
  v12 = *((_QWORD *)this + 10);
  if ( v12 )
  {
    *(_DWORD *)(v12 + 8) = 0;
    *(_QWORD *)v12 = 0;
  }
  v13 = *((_QWORD *)this + 11);
  if ( v13 )
  {
    *(_DWORD *)(v13 + 8) = 0;
    *(_QWORD *)v13 = 0;
  }
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 27) = 0;
LABEL_20:
  LeaveCriticalSection(v2);
  return v10;
}

```

## disassembly

```asm
0x18004fbb0  push    rbx
0x18004fbb2  push    rbp
0x18004fbb3  push    rsi
0x18004fbb4  push    rdi
0x18004fbb5  sub     rsp, 28h
0x18004fbb9  mov     rbx, rcx
0x18004fbbc  lea     rsi, [rcx+0E0h]
0x18004fbc3  mov     [rsp+48h+arg_0], rsi
0x18004fbc8  mov     rcx, rsi; lpCriticalSection
0x18004fbcb  call    cs:__imp_EnterCriticalSection
0x18004fbd2  nop     dword ptr [rax+rax+00h]
0x18004fbd7  nop
0x18004fbd8  mov     rdi, [rbx+50h]
0x18004fbdc  xor     ebp, ebp
0x18004fbde  test    rdi, rdi
0x18004fbe1  jz      short loc_18004FC0D
0x18004fbe3  mov     rcx, [rdi+18h]; Block
0x18004fbe7  test    rcx, rcx
0x18004fbea  jz      short loc_18004FBFC
0x18004fbec  call    cs:__imp__aligned_free
0x18004fbf3  nop     dword ptr [rax+rax+00h]
0x18004fbf8  mov     [rdi+18h], rbp
0x18004fbfc  mov     edx, 20h ; ' '
0x18004fc01  mov     rcx, rdi; Block
0x18004fc04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004fc09  mov     [rbx+50h], rbp
0x18004fc0d  mov     rdi, [rbx+58h]
0x18004fc11  test    rdi, rdi
0x18004fc14  jz      short loc_18004FC40
0x18004fc16  mov     rcx, [rdi+18h]; Block
0x18004fc1a  test    rcx, rcx
0x18004fc1d  jz      short loc_18004FC2F
0x18004fc1f  call    cs:__imp__aligned_free
0x18004fc26  nop     dword ptr [rax+rax+00h]
0x18004fc2b  mov     [rdi+18h], rbp
0x18004fc2f  mov     edx, 20h ; ' '
0x18004fc34  mov     rcx, rdi; Block
0x18004fc37  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004fc3c  mov     [rbx+58h], rbp
0x18004fc40  mov     eax, [rbx+34h]
0x18004fc43  sub     eax, [rbx+38h]
0x18004fc46  mov     [rbx+4Ch], eax
0x18004fc49  mov     edx, [rbx+40h]
0x18004fc4c  mov     eax, [rbx+44h]
0x18004fc4f  lea     r8d, [rax+rdx*2]
0x18004fc53  add     r8d, [rbx+34h]
0x18004fc57  mov     [rbx+48h], r8d
0x18004fc5b  mov     ecx, 20h ; ' '; Size
0x18004fc60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fc65  mov     rdi, rax
0x18004fc68  mov     [rsp+48h+arg_0], rax
0x18004fc6d  test    rax, rax
0x18004fc70  jz      loc_18004FCF9
0x18004fc76  movzx   ecx, word ptr [rbx+10h]
0x18004fc7a  mov     [rax], rbp
0x18004fc7d  mov     [rax+8], ebp
0x18004fc80  mov     [rax+0Ch], ecx
0x18004fc83  lea     ecx, [rcx+rcx*2]
0x18004fc86  shl     ecx, 0Ch
0x18004fc89  mov     [rax+10h], ecx
0x18004fc8c  mov     [rax+18h], rbp
0x18004fc90  mov     [rbx+50h], rax
0x18004fc94  test    rax, rax
0x18004fc97  jz      short loc_18004FCFD
0x18004fc99  cmp     [rax+18h], rbp
0x18004fc9d  jz      short loc_18004FCA6
0x18004fc9f  mov     edi, 8000FFFFh
0x18004fca4  jmp     short loc_18004FD02
0x18004fca6  movsxd  rcx, dword ptr [rax+10h]; Size
0x18004fcaa  mov     edx, 10h; Alignment
0x18004fcaf  call    cs:__imp__aligned_malloc
0x18004fcb6  nop     dword ptr [rax+rax+00h]
0x18004fcbb  mov     [rdi+18h], rax
0x18004fcbf  test    rax, rax
0x18004fcc2  jz      short loc_18004FCFD
0x18004fcc4  mov     edi, ebp
0x18004fcc6  mov     byte ptr [rbx+16h], 1
0x18004fcca  mov     rax, [rbx+50h]
0x18004fcce  test    rax, rax
0x18004fcd1  jz      short loc_18004FCD9
0x18004fcd3  mov     [rax+8], ebp
0x18004fcd6  mov     [rax], rbp
0x18004fcd9  mov     rax, [rbx+58h]
0x18004fcdd  test    rax, rax
0x18004fce0  jz      short loc_18004FCE8
0x18004fce2  mov     [rax+8], ebp
0x18004fce5  mov     [rax], rbp
0x18004fce8  mov     [rbx+60h], rbp
0x18004fcec  mov     [rbx+68h], rbp
0x18004fcf0  mov     [rbx+0D8h], rbp
0x18004fcf7  jmp     short loc_18004FD02
0x18004fcf9  mov     [rbx+50h], rbp
0x18004fcfd  mov     edi, 8007000Eh
0x18004fd02  mov     rcx, rsi; lpCriticalSection
0x18004fd05  call    cs:__imp_LeaveCriticalSection
0x18004fd0c  nop     dword ptr [rax+rax+00h]
0x18004fd11  mov     eax, edi
0x18004fd13  add     rsp, 28h
0x18004fd17  pop     rdi
0x18004fd18  pop     rsi
0x18004fd19  pop     rbp
0x18004fd1a  pop     rbx
0x18004fd1b  retn
```
