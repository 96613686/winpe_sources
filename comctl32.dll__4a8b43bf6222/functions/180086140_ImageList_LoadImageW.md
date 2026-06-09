# ImageList_LoadImageW

- ea: `0x180086140`
- end: `0x180086264`
- name: `ImageList_LoadImageW`
- size: `292`
- prototype: `HIMAGELIST __stdcall(HINSTANCE hi, LPCWSTR lpbmp, int cx, int cGrow, COLORREF crMask, UINT uType, UINT uFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005eb28`
- `0x1800860a0`

## callees

- `0x180085390`
- `0x180085430`
- `0x1800857d0`
- `0x180085890`
- `0x180086140`

## import_xrefs

- `GDI32!DeleteObject` at `0x18008624f`
- `GDI32!DeleteObject` at `0x18008624f`
- `GDI32!GetObjectW` at `0x180086198`
- `GDI32!GetObjectW` at `0x180086198`
- `KERNEL32!EnterCriticalSection` at `0x1800861c1`
- `KERNEL32!EnterCriticalSection` at `0x1800861c1`
- `KERNEL32!LeaveCriticalSection` at `0x180086246`
- `KERNEL32!LeaveCriticalSection` at `0x180086246`
- `USER32!LoadImageW` at `0x18008617b`
- `USER32!LoadImageW` at `0x18008617b`

## pseudocode

```c
HIMAGELIST __stdcall ImageList_LoadImageW(
        HINSTANCE hi,
        LPCWSTR lpbmp,
        int cx,
        int cGrow,
        COLORREF crMask,
        UINT uType,
        UINT uFlags)
{
  struct _IMAGELIST *v9; // rbx
  HBITMAP ImageW; // rax
  HBITMAP v11; // rdi
  int v12; // ebx
  int v13; // r14d
  UINT v14; // r8d
  struct _IMAGELIST *v15; // rax
  int v16; // eax
  __int128 pv; // [rsp+30h] [rbp-48h] BYREF
  __int128 v19; // [rsp+40h] [rbp-38h]

  v9 = 0;
  pv = 0;
  v19 = 0;
  ImageW = (HBITMAP)LoadImageW(hi, lpbmp, uType, 0, 0, uFlags);
  v11 = ImageW;
  if ( ImageW )
  {
    if ( GetObjectW(ImageW, 32, &pv) == 32 )
    {
      v12 = DWORD2(pv);
      if ( !cx )
        cx = DWORD2(pv);
      v13 = SDWORD1(pv) / cx;
      EnterCriticalSection(&g_csDll);
      if ( *((_QWORD *)&v19 + 1) )
        v14 = (crMask != -1) | BYTE2(v19) & 0xFE;
      else
        v14 = crMask != -1;
      v15 = ImageList_Create(cx, v12, v14, v13, cGrow);
      v9 = v15;
      if ( v15 )
      {
        if ( crMask == -1 )
          v16 = ImageList_Add(v15, v11, 0);
        else
          v16 = ImageList_AddMasked(v15, v11, crMask);
        if ( v16 < 0 )
        {
          ImageList_Destroy(v9);
          v9 = 0;
        }
      }
      LeaveCriticalSection(&g_csDll);
    }
    DeleteObject(v11);
  }
  return v9;
}

```

## disassembly

```asm
0x180086140  push    rbx
0x180086142  push    rbp
0x180086143  push    rdi
0x180086144  push    r14
0x180086146  push    r15
0x180086148  sub     rsp, 50h
0x18008614c  mov     eax, [rsp+78h+uFlags]
0x180086153  xorps   xmm0, xmm0
0x180086156  mov     r15d, r9d
0x180086159  mov     [rsp+78h+fuLoad], eax; fuLoad
0x18008615d  mov     ebp, r8d
0x180086160  xor     ebx, ebx
0x180086162  mov     r8d, [rsp+78h+uType]; type
0x18008616a  xor     r9d, r9d; cx
0x18008616d  movups  [rsp+78h+pv], xmm0
0x180086172  mov     [rsp+78h+cy], ebx; cy
0x180086176  movups  [rsp+78h+var_38], xmm0
0x18008617b  call    cs:__imp_LoadImageW
0x180086181  mov     rdi, rax
0x180086184  test    rax, rax
0x180086187  jz      loc_180086255
0x18008618d  lea     r8, [rsp+78h+pv]; pv
0x180086192  mov     rcx, rax; h
0x180086195  lea     edx, [rbx+20h]; c
0x180086198  call    cs:__imp_GetObjectW
0x18008619e  cmp     eax, 20h ; ' '
0x1800861a1  jnz     loc_18008624C
0x1800861a7  mov     eax, dword ptr [rsp+78h+pv+4]
0x1800861ab  lea     rcx, g_csDll; lpCriticalSection
0x1800861b2  mov     ebx, dword ptr [rsp+78h+pv+8]
0x1800861b6  cdq
0x1800861b7  test    ebp, ebp
0x1800861b9  cmovz   ebp, ebx
0x1800861bc  idiv    ebp
0x1800861be  mov     r14d, eax
0x1800861c1  call    cs:__imp_EnterCriticalSection
0x1800861c7  xor     ecx, ecx
0x1800861c9  cmp     [rsp+78h+crMask], 0FFFFFFFFh
0x1800861d1  setnz   cl
0x1800861d4  cmp     qword ptr [rsp+78h+var_38+8], 0
0x1800861da  jz      short loc_1800861EE
0x1800861dc  movzx   r8d, word ptr [rsp+78h+var_38+2]
0x1800861e2  and     r8d, 0FEh
0x1800861e9  or      r8d, ecx
0x1800861ec  jmp     short loc_1800861F1
0x1800861ee  mov     r8d, ecx; flags
0x1800861f1  mov     r9d, r14d; cInitial
0x1800861f4  mov     [rsp+78h+cy], r15d; cGrow
0x1800861f9  mov     edx, ebx; cy
0x1800861fb  mov     ecx, ebp; cx
0x1800861fd  call    ImageList_Create
0x180086202  mov     rbx, rax
0x180086205  test    rax, rax
0x180086208  jz      short loc_18008623F
0x18008620a  cmp     [rsp+78h+crMask], 0FFFFFFFFh
0x180086212  mov     rdx, rdi; hbmImage
0x180086215  mov     rcx, rax; himl
0x180086218  jnz     short loc_180086224
0x18008621a  xor     r8d, r8d; hbmMask
0x18008621d  call    ImageList_Add
0x180086222  jmp     short loc_180086231
0x180086224  mov     r8d, [rsp+78h+crMask]; crMask
0x18008622c  call    ImageList_AddMasked
0x180086231  test    eax, eax
0x180086233  jns     short loc_18008623F
0x180086235  mov     rcx, rbx; himl
0x180086238  call    ImageList_Destroy
0x18008623d  xor     ebx, ebx
0x18008623f  lea     rcx, g_csDll; lpCriticalSection
0x180086246  call    cs:__imp_LeaveCriticalSection
0x18008624c  mov     rcx, rdi; ho
0x18008624f  call    cs:__imp_DeleteObject
0x180086255  mov     rax, rbx
0x180086258  add     rsp, 50h
0x18008625c  pop     r15
0x18008625e  pop     r14
0x180086260  pop     rdi
0x180086261  pop     rbp
0x180086262  pop     rbx
0x180086263  retn
```
