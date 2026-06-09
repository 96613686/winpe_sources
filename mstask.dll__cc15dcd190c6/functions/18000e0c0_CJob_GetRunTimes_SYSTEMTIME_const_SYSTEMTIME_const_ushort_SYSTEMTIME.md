# CJob::GetRunTimes(_SYSTEMTIME * const,_SYSTEMTIME * const,ushort *,_SYSTEMTIME * *)

- ea: `0x18000e0c0`
- end: `0x18000e228`
- name: `?GetRunTimes@CJob@@UEAAJQEAU_SYSTEMTIME@@0PEAGPEAPEAU2@@Z`
- size: `360`
- prototype: `int(CJob *__hidden this, struct _SYSTEMTIME *const, struct _SYSTEMTIME *const, unsigned __int16 *, struct _SYSTEMTIME **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800092a8`
- `0x180009e30`
- `0x18000e0c0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e1d5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000e1d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e19a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e19a`

## pseudocode

```c
__int64 __fastcall CJob::GetRunTimes(
        CJob *this,
        struct _SYSTEMTIME *const a2,
        struct _SYSTEMTIME *const a3,
        unsigned __int16 *a4,
        struct _SYSTEMTIME **a5)
{
  unsigned __int16 v5; // r15
  unsigned int RunTimesP; // ebx
  unsigned __int16 v8; // si
  __int64 v9; // rcx
  struct _SYSTEMTIME *v10; // rax
  unsigned __int16 v11; // ax
  void ***v12; // rbx
  unsigned __int16 v13; // r8
  unsigned __int16 v14; // dx
  unsigned __int16 *v16; // [rsp+30h] [rbp-71h]
  void **v17; // [rsp+40h] [rbp-61h] BYREF
  void ***v18; // [rsp+48h] [rbp-59h]
  void ***v19; // [rsp+50h] [rbp-51h]
  __int64 v20; // [rsp+58h] [rbp-49h]
  __int64 v21; // [rsp+60h] [rbp-41h]
  __int64 v22; // [rsp+68h] [rbp-39h]
  __int128 v23; // [rsp+70h] [rbp-31h]
  int v24; // [rsp+80h] [rbp-21h]
  __int64 v25; // [rsp+88h] [rbp-19h]
  __int128 v26; // [rsp+90h] [rbp-11h]
  int v27; // [rsp+A0h] [rbp-1h]
  int v28; // [rsp+A4h] [rbp+3h]
  __int16 v29; // [rsp+A8h] [rbp+7h]
  __int64 v30; // [rsp+ACh] [rbp+Bh]
  int v31; // [rsp+B4h] [rbp+13h]

  v5 = *a4;
  v17 = &CRun::`vftable';
  v21 = 0x7FFFFFFFFFFFFFFFLL;
  v22 = 0x7FFFFFFFFFFFFFFFLL;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v20 = 0;
  v18 = &v17;
  v19 = &v17;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = -1;
  if ( (unsigned __int16)(v5 - 1) > 0x59Fu )
  {
    RunTimesP = -2147024809;
  }
  else
  {
    *a5 = 0;
    *a4 = 0;
    RunTimesP = CJob::GetRunTimesP(this, a2, a3, a4, v5, (struct CTimeRunList *)&v17, v16);
    if ( RunTimesP )
    {
      *a4 = 0;
    }
    else
    {
      v8 = *a4;
      v9 = *a4;
      *a4 = 0;
      v10 = (struct _SYSTEMTIME *)CoTaskMemAlloc(16 * v9);
      *a5 = v10;
      if ( v10 )
      {
        v11 = *a4;
        if ( *a4 >= v8 )
        {
          v14 = *a4;
        }
        else
        {
          v12 = v18;
          v13 = *a4;
          do
          {
            if ( !*((_DWORD *)v12 + 6) )
            {
              v14 = v13;
              if ( !*((_DWORD *)v12 + 7) )
                break;
            }
            FileTimeToSystemTime((const FILETIME *)v12 + 3, &(*a5)[v11]);
            v11 = ++*a4;
            v12 = (void ***)v12[1];
            v13 = *a4;
            v14 = *a4;
          }
          while ( *a4 < v8 );
        }
        RunTimesP = v14 < v5;
      }
      else
      {
        RunTimesP = -2147024882;
      }
    }
  }
  CRunList::~CRunList((CRunList *)&v17);
  return RunTimesP;
}

```

## disassembly

```asm
0x18000e0c0  push    rbp
0x18000e0c2  push    rbx
0x18000e0c3  push    rsi
0x18000e0c4  push    rdi
0x18000e0c5  push    r14
0x18000e0c7  push    r15
0x18000e0c9  lea     rbp, [rsp-27h]
0x18000e0ce  sub     rsp, 0C8h
0x18000e0d5  movzx   r15d, word ptr [r9]
0x18000e0d9  lea     rax, ??_7CRun@@6B@; const CRun::`vftable'
0x18000e0e0  mov     [rbp+4Fh+var_B0], rax
0x18000e0e4  xorps   xmm0, xmm0
0x18000e0e7  mov     rax, cs:qword_18001E4F0
0x18000e0ee  mov     rdi, r9
0x18000e0f1  mov     [rbp+4Fh+var_90], rax
0x18000e0f5  mov     r9d, 59Fh
0x18000e0fb  mov     [rbp+4Fh+var_88], rax
0x18000e0ff  xor     eax, eax
0x18000e101  mov     [rbp+4Fh+var_48], ax
0x18000e105  mov     [rbp+4Fh+var_44], rax
0x18000e109  mov     [rbp+4Fh+var_3C], eax
0x18000e10c  mov     [rbp+4Fh+var_98], rax
0x18000e110  lea     rax, [rbp+4Fh+var_B0]
0x18000e114  mov     [rbp+4Fh+var_A8], rax
0x18000e118  lea     rax, [rbp+4Fh+var_B0]
0x18000e11c  mov     [rbp+4Fh+var_A0], rax
0x18000e120  lea     eax, [r15-1]
0x18000e124  movdqa  [rbp+4Fh+var_80], xmm0
0x18000e129  mov     [rbp+4Fh+var_70], 0
0x18000e130  mov     [rbp+4Fh+var_68], 0
0x18000e138  movdqa  [rbp+4Fh+var_60], xmm0
0x18000e13d  mov     [rbp+4Fh+var_50], 0
0x18000e144  mov     [rbp+4Fh+var_4C], 0FFFFFFFFh
0x18000e14b  cmp     ax, r9w
0x18000e14f  ja      loc_18000E208
0x18000e155  mov     r14, [rbp+4Fh+arg_20]
0x18000e159  xor     eax, eax
0x18000e15b  mov     r9, rdi; unsigned __int16 *
0x18000e15e  mov     qword ptr [r14], 0
0x18000e165  mov     [rdi], ax
0x18000e168  lea     rax, [rbp+4Fh+var_B0]
0x18000e16c  mov     [rsp+0F0h+var_C8], rax; struct CTimeRunList *
0x18000e171  mov     [rsp+0F0h+var_D0], r15w; unsigned __int16
0x18000e177  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x18000e17c  mov     ebx, eax
0x18000e17e  test    eax, eax
0x18000e180  jz      short loc_18000E18C
0x18000e182  xor     ecx, ecx
0x18000e184  mov     [rdi], cx
0x18000e187  jmp     loc_18000E20D
0x18000e18c  movzx   esi, word ptr [rdi]
0x18000e18f  xor     eax, eax
0x18000e191  mov     ecx, esi
0x18000e193  mov     [rdi], ax
0x18000e196  shl     rcx, 4; cb
0x18000e19a  call    cs:__imp_CoTaskMemAlloc
0x18000e1a0  mov     [r14], rax
0x18000e1a3  test    rax, rax
0x18000e1a6  jz      short loc_18000E201
0x18000e1a8  movzx   eax, word ptr [rdi]
0x18000e1ab  cmp     ax, si
0x18000e1ae  jnb     short loc_18000E1F3
0x18000e1b0  mov     rbx, [rbp+4Fh+var_A8]
0x18000e1b4  movzx   r8d, ax
0x18000e1b8  lea     rcx, [rbx+18h]; lpFileTime
0x18000e1bc  cmp     dword ptr [rcx], 0
0x18000e1bf  jnz     short loc_18000E1CB
0x18000e1c1  cmp     dword ptr [rbx+1Ch], 0
0x18000e1c5  movzx   edx, r8w
0x18000e1c9  jz      short loc_18000E1F6
0x18000e1cb  movzx   edx, ax
0x18000e1ce  shl     rdx, 4
0x18000e1d2  add     rdx, [r14]; lpSystemTime
0x18000e1d5  call    cs:__imp_FileTimeToSystemTime
0x18000e1db  inc     word ptr [rdi]
0x18000e1de  movzx   eax, word ptr [rdi]
0x18000e1e1  mov     rbx, [rbx+8]
0x18000e1e5  movzx   r8d, ax
0x18000e1e9  movzx   edx, ax
0x18000e1ec  cmp     ax, si
0x18000e1ef  jb      short loc_18000E1B8
0x18000e1f1  jmp     short loc_18000E1F6
0x18000e1f3  movzx   edx, ax
0x18000e1f6  xor     ebx, ebx
0x18000e1f8  cmp     dx, r15w
0x18000e1fc  setb    bl
0x18000e1ff  jmp     short loc_18000E20D
0x18000e201  mov     ebx, 8007000Eh
0x18000e206  jmp     short loc_18000E20D
0x18000e208  mov     ebx, 80070057h
0x18000e20d  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000e211  call    ??1CRunList@@QEAA@XZ; CRunList::~CRunList(void)
0x18000e216  mov     eax, ebx
0x18000e218  add     rsp, 0C8h
0x18000e21f  pop     r15
0x18000e221  pop     r14
0x18000e223  pop     rdi
0x18000e224  pop     rsi
0x18000e225  pop     rbx
0x18000e226  pop     rbp
0x18000e227  retn
```
