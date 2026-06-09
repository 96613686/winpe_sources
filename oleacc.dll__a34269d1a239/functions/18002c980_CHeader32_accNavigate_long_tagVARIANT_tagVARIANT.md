# CHeader32::accNavigate(long,tagVARIANT,tagVARIANT *)

- ea: `0x18002c980`
- end: `0x18002cb8f`
- name: `?accNavigate@CHeader32@@UEAAJJUtagVARIANT@@PEAU2@@Z`
- size: `527`
- prototype: `__int64 __fastcall(CHeader32 *__hidden this, int, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800283e0`
- `0x18002c980`
- `0x180045b30`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002cacc`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002cacc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002caa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002caa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cb66`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ca41`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ca41`

## pseudocode

```c
__int64 __fastcall CHeader32::accNavigate(HWND *this, int a2, struct tagVARIANT *a3, struct tagVARIANT *a4)
{
  int v8; // edx
  IRecordInfo *pRecInfo; // xmm1_8
  void *v11; // r14
  HLOCAL v12; // rbp
  int v13; // esi
  int v14; // esi
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // esi
  __int64 lVal; // rcx
  __int64 v23; // rcx
  int i; // eax
  struct tagVARIANT v25; // [rsp+40h] [rbp-68h] BYREF
  HANDLE hProcess; // [rsp+B0h] [rbp+8h] BYREF

  hProcess = 0;
  a4->vt = 0;
  if ( (*((unsigned int (__fastcall **)(HWND *, struct tagVARIANT *))*this + 30))(this, a3)
    && (unsigned int)ValidateNavDir(a2, a3->lVal) )
  {
    if ( !v8 && a2 < 7 )
    {
      pRecInfo = a3->pRecInfo;
      *(_OWORD *)&v25.vt = *(_OWORD *)&a3->vt;
      v25.pRecInfo = pRecInfo;
      return CClient::accNavigate((CClient *)this, a2, &v25, a4);
    }
    v11 = SharedAlloc((unsigned int)(4 * *((_DWORD *)this + 23)), this[10], &hProcess);
    if ( !v11 )
      return 2147942414LL;
    v12 = LocalAlloc(0x40u, 4LL * *((int *)this + 23));
    if ( !v12 )
    {
      SharedFree(v11, hProcess);
      return 2147942414LL;
    }
    v13 = CAccessible::AccSendMessageTimeout(
            (CAccessible *)this,
            0,
            this[10],
            0x1211u,
            *((int *)this + 23),
            (__int64)v11,
            0);
    if ( v13 < 0 )
    {
      SharedFree(v11, hProcess);
      LocalFree(v12);
      return (unsigned int)v13;
    }
    v14 = 0;
    ReadProcessMemory(hProcess, v11, v12, (unsigned int)(4 * *((_DWORD *)this + 23)), 0);
    v15 = a2 - 1;
    if ( !v15 )
      goto LABEL_32;
    v16 = v15 - 1;
    if ( !v16 )
      goto LABEL_32;
    v17 = v16 - 1;
    if ( !v17 )
      goto LABEL_23;
    v18 = v17 - 1;
    if ( !v18 || (v19 = v18 - 1) == 0 )
    {
      lVal = a3->lVal;
      if ( (int)lVal - 1 < *((_DWORD *)this + 23) )
      {
        v14 = *((_DWORD *)v12 + lVal - 1) + 1;
        if ( v14 < *((_DWORD *)this + 23) )
        {
LABEL_27:
          for ( i = 0; i < *((_DWORD *)this + 23); ++i )
          {
            if ( *((_DWORD *)v12 + i) == v14 )
            {
              a4->vt = 3;
              a4->lVal = i + 1;
              break;
            }
          }
        }
      }
LABEL_32:
      SharedFree(v11, hProcess);
      LocalFree(v12);
      return a4->vt == 0;
    }
    v20 = v19 - 1;
    if ( v20 )
    {
      if ( v20 != 2 )
        goto LABEL_27;
      v21 = *((_DWORD *)this + 23);
    }
    else
    {
LABEL_23:
      v23 = a3->lVal;
      if ( (int)v23 - 1 >= *((_DWORD *)this + 23) )
        goto LABEL_32;
      v21 = *((_DWORD *)v12 + v23 - 1);
    }
    if ( v21 )
    {
      v14 = v21 - 1;
      goto LABEL_27;
    }
    goto LABEL_32;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002c980  mov     rax, rsp
0x18002c983  push    rbx
0x18002c984  push    rbp
0x18002c985  push    rsi
0x18002c986  push    rdi
0x18002c987  push    r12
0x18002c989  push    r13
0x18002c98b  push    r14
0x18002c98d  push    r15
0x18002c98f  sub     rsp, 68h
0x18002c993  xor     r13d, r13d
0x18002c996  mov     ebx, edx
0x18002c998  mov     [rax+8], r13
0x18002c99c  mov     rdx, r8
0x18002c99f  mov     [r9], r13w
0x18002c9a3  mov     r12, r9
0x18002c9a6  mov     rax, [rcx]
0x18002c9a9  mov     r15, r8
0x18002c9ac  mov     rdi, rcx
0x18002c9af  mov     rax, [rax+0F0h]
0x18002c9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9bb  test    eax, eax
0x18002c9bd  jz      loc_18002CB79
0x18002c9c3  mov     edx, [r15+8]; int
0x18002c9c7  mov     ecx, ebx; int
0x18002c9c9  call    ?ValidateNavDir@@YAHJJ@Z; ValidateNavDir(long,long)
0x18002c9ce  test    eax, eax
0x18002c9d0  jz      loc_18002CB79
0x18002c9d6  test    edx, edx
0x18002c9d8  jnz     short loc_18002CA0B
0x18002c9da  cmp     ebx, 7
0x18002c9dd  jge     short loc_18002CA0B
0x18002c9df  movups  xmm0, xmmword ptr [r15]
0x18002c9e3  lea     r8, [rsp+0A8h+var_68]; struct tagVARIANT *
0x18002c9e8  mov     r9, r12; struct tagVARIANT *
0x18002c9eb  movsd   xmm1, qword ptr [r15+10h]
0x18002c9f1  mov     edx, ebx; int
0x18002c9f3  mov     rcx, rdi; this
0x18002c9f6  movaps  xmmword ptr [rsp+0A8h+var_68], xmm0
0x18002c9fb  movsd   qword ptr [rsp+0A8h+var_68+10h], xmm1
0x18002ca01  call    ?accNavigate@CClient@@UEAAJJUtagVARIANT@@PEAU2@@Z; CClient::accNavigate(long,tagVARIANT,tagVARIANT *)
0x18002ca06  jmp     loc_18002CB7E
0x18002ca0b  mov     ecx, [rdi+5Ch]
0x18002ca0e  lea     r8, [rsp+0A8h+hProcess]; void **
0x18002ca16  mov     rdx, [rdi+50h]; HWND
0x18002ca1a  shl     ecx, 2; dwSize
0x18002ca1d  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002ca22  mov     r14, rax
0x18002ca25  test    rax, rax
0x18002ca28  jnz     short loc_18002CA34
0x18002ca2a  mov     eax, 8007000Eh
0x18002ca2f  jmp     loc_18002CB7E
0x18002ca34  movsxd  rdx, dword ptr [rdi+5Ch]
0x18002ca38  mov     ecx, 40h ; '@'; uFlags
0x18002ca3d  shl     rdx, 2; uBytes
0x18002ca41  call    cs:__imp_LocalAlloc
0x18002ca47  mov     rbp, rax
0x18002ca4a  test    rax, rax
0x18002ca4d  jnz     short loc_18002CA61
0x18002ca4f  mov     rdx, [rsp+0A8h+hProcess]; hProcess
0x18002ca57  mov     rcx, r14; lpAddress
0x18002ca5a  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002ca5f  jmp     short loc_18002CA2A
0x18002ca61  movsxd  rax, dword ptr [rdi+5Ch]
0x18002ca65  mov     r9d, 1211h; unsigned int
0x18002ca6b  mov     r8, [rdi+50h]; HWND
0x18002ca6f  xor     edx, edx; bool
0x18002ca71  mov     [rsp+0A8h+var_78], r13; __int64 *
0x18002ca76  mov     rcx, rdi; this
0x18002ca79  mov     [rsp+0A8h+var_80], r14; __int64
0x18002ca7e  mov     [rsp+0A8h+lpNumberOfBytesRead], rax; unsigned __int64
0x18002ca83  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002ca88  mov     esi, eax
0x18002ca8a  test    eax, eax
0x18002ca8c  jns     short loc_18002CAAE
0x18002ca8e  mov     rdx, [rsp+0A8h+hProcess]; hProcess
0x18002ca96  mov     rcx, r14; lpAddress
0x18002ca99  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002ca9e  mov     rcx, rbp; hMem
0x18002caa1  call    cs:__imp_LocalFree
0x18002caa7  mov     eax, esi
0x18002caa9  jmp     loc_18002CB7E
0x18002caae  mov     r9d, [rdi+5Ch]
0x18002cab2  mov     r8, rbp; lpBuffer
0x18002cab5  mov     rcx, [rsp+0A8h+hProcess]; hProcess
0x18002cabd  mov     rdx, r14; lpBaseAddress
0x18002cac0  shl     r9d, 2; nSize
0x18002cac4  mov     esi, r13d
0x18002cac7  mov     [rsp+0A8h+lpNumberOfBytesRead], r13; lpNumberOfBytesRead
0x18002cacc  call    cs:__imp_ReadProcessMemory
0x18002cad2  sub     ebx, 1
0x18002cad5  jz      short loc_18002CB53
0x18002cad7  sub     ebx, 1
0x18002cada  jz      short loc_18002CB53
0x18002cadc  sub     ebx, 1
0x18002cadf  jz      short loc_18002CB18
0x18002cae1  sub     ebx, 1
0x18002cae4  jz      short loc_18002CAFF
0x18002cae6  sub     ebx, 1
0x18002cae9  jz      short loc_18002CAFF
0x18002caeb  sub     ebx, 1
0x18002caee  jz      short loc_18002CB18
0x18002caf0  sub     ebx, 1
0x18002caf3  jz      short loc_18002CB2E
0x18002caf5  cmp     ebx, 1
0x18002caf8  jnz     short loc_18002CB2E
0x18002cafa  mov     esi, [rdi+5Ch]
0x18002cafd  jmp     short loc_18002CB28
0x18002caff  movsxd  rcx, dword ptr [r15+8]
0x18002cb03  lea     eax, [rcx-1]
0x18002cb06  cmp     eax, [rdi+5Ch]
0x18002cb09  jge     short loc_18002CB53
0x18002cb0b  mov     esi, [rbp+rcx*4-4]
0x18002cb0f  inc     esi
0x18002cb11  cmp     esi, [rdi+5Ch]
0x18002cb14  jge     short loc_18002CB53
0x18002cb16  jmp     short loc_18002CB2E
0x18002cb18  movsxd  rcx, dword ptr [r15+8]
0x18002cb1c  lea     eax, [rcx-1]
0x18002cb1f  cmp     eax, [rdi+5Ch]
0x18002cb22  jge     short loc_18002CB53
0x18002cb24  mov     esi, [rbp+rcx*4-4]
0x18002cb28  test    esi, esi
0x18002cb2a  jz      short loc_18002CB53
0x18002cb2c  dec     esi
0x18002cb2e  mov     edx, [rdi+5Ch]
0x18002cb31  mov     eax, r13d
0x18002cb34  cmp     eax, edx
0x18002cb36  jge     short loc_18002CB53
0x18002cb38  lea     ecx, [rax+1]
0x18002cb3b  cdqe
0x18002cb3d  cmp     [rbp+rax*4+0], esi
0x18002cb41  jz      short loc_18002CB47
0x18002cb43  mov     eax, ecx
0x18002cb45  jmp     short loc_18002CB34
0x18002cb47  mov     word ptr [r12], 3
0x18002cb4e  mov     [r12+8], ecx
0x18002cb53  mov     rdx, [rsp+0A8h+hProcess]; hProcess
0x18002cb5b  mov     rcx, r14; lpAddress
0x18002cb5e  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002cb63  mov     rcx, rbp; hMem
0x18002cb66  call    cs:__imp_LocalFree
0x18002cb6c  cmp     [r12], r13w
0x18002cb71  mov     eax, r13d
0x18002cb74  setz    al
0x18002cb77  jmp     short loc_18002CB7E
0x18002cb79  mov     eax, 80070057h
0x18002cb7e  add     rsp, 68h
0x18002cb82  pop     r15
0x18002cb84  pop     r14
0x18002cb86  pop     r13
0x18002cb88  pop     r12
0x18002cb8a  pop     rdi
0x18002cb8b  pop     rsi
0x18002cb8c  pop     rbp
0x18002cb8d  pop     rbx
0x18002cb8e  retn
```
