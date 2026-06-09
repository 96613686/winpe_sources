# CImageList::_SetBkColor(ulong)

- ea: `0x180084e38`
- end: `0x180084ef1`
- name: `?_SetBkColor@CImageList@@QEAAKK@Z`
- size: `185`
- prototype: `unsigned int __fastcall(CImageList *__hidden this, COLORREF color)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180082b30`
- `0x18008462c`

## callees

- `0x180081454`
- `0x180084d30`
- `0x180084e38`

## import_xrefs

- `GDI32!DeleteObject` at `0x180084e6d`
- `GDI32!DeleteObject` at `0x180084e6d`
- `GDI32!GetStockObject` at `0x180084e83`
- `GDI32!GetStockObject` at `0x180084e83`
- `GDI32!CreateSolidBrush` at `0x180084e96`
- `GDI32!CreateSolidBrush` at `0x180084e96`
- `KERNEL32!EnterCriticalSection` at `0x180084e5e`
- `KERNEL32!EnterCriticalSection` at `0x180084e5e`
- `KERNEL32!LeaveCriticalSection` at `0x180084ed9`
- `KERNEL32!LeaveCriticalSection` at `0x180084ed9`

## pseudocode

```c
__int64 __fastcall CImageList::_SetBkColor(CImageList *this, COLORREF color)
{
  __int64 result; // rax
  void *v5; // rcx
  unsigned int v6; // esi
  BOOL v7; // ecx
  HBRUSH SolidBrush; // rax
  COLORREF v9; // ebx
  HDC v10; // rcx
  int v11; // r8d

  result = *((unsigned int *)this + 22);
  if ( (_DWORD)result != color )
  {
    EnterCriticalSection(&g_csDll);
    v5 = (void *)*((_QWORD *)this + 12);
    if ( v5 )
      DeleteObject(v5);
    v6 = *((_DWORD *)this + 22);
    *((_DWORD *)this + 22) = color;
    if ( color == -1 )
    {
      *((_QWORD *)this + 12) = GetStockObject(4);
      v7 = 1;
    }
    else
    {
      SolidBrush = CreateSolidBrush(color);
      v9 = *((_DWORD *)this + 22);
      v10 = (HDC)*((_QWORD *)this + 15);
      *((_QWORD *)this + 12) = SolidBrush;
      v7 = GetNearestColor32(v10, v9) == v9;
    }
    *((_DWORD *)this + 12) = v7;
    v11 = *((_DWORD *)this + 14);
    if ( v11 > 0 )
      CImageList::_ResetBkColor(this, 0, v11 - 1, *((_DWORD *)this + 22));
    LeaveCriticalSection(&g_csDll);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180084e38  mov     [rsp+arg_0], rbx
0x180084e3d  mov     [rsp+arg_8], rsi
0x180084e42  push    rdi
0x180084e43  sub     rsp, 20h
0x180084e47  mov     eax, [rcx+58h]
0x180084e4a  mov     ebx, edx
0x180084e4c  mov     rdi, rcx
0x180084e4f  cmp     eax, edx
0x180084e51  jz      loc_180084EE1
0x180084e57  lea     rcx, g_csDll; lpCriticalSection
0x180084e5e  call    cs:__imp_EnterCriticalSection
0x180084e64  mov     rcx, [rdi+60h]; ho
0x180084e68  test    rcx, rcx
0x180084e6b  jz      short loc_180084E73
0x180084e6d  call    cs:__imp_DeleteObject
0x180084e73  mov     esi, [rdi+58h]
0x180084e76  mov     [rdi+58h], ebx
0x180084e79  cmp     ebx, 0FFFFFFFFh
0x180084e7c  jnz     short loc_180084E94
0x180084e7e  mov     ecx, 4; i
0x180084e83  call    cs:__imp_GetStockObject
0x180084e89  mov     [rdi+60h], rax
0x180084e8d  mov     ecx, 1
0x180084e92  jmp     short loc_180084EB5
0x180084e94  mov     ecx, ebx; color
0x180084e96  call    cs:__imp_CreateSolidBrush
0x180084e9c  mov     ebx, [rdi+58h]
0x180084e9f  mov     edx, ebx; color
0x180084ea1  mov     rcx, [rdi+78h]; hdc
0x180084ea5  mov     [rdi+60h], rax
0x180084ea9  call    ?GetNearestColor32@@YAKPEAUHDC__@@K@Z; GetNearestColor32(HDC__ *,ulong)
0x180084eae  xor     ecx, ecx
0x180084eb0  cmp     eax, ebx
0x180084eb2  setz    cl
0x180084eb5  mov     [rdi+30h], ecx
0x180084eb8  mov     r8d, [rdi+38h]
0x180084ebc  test    r8d, r8d
0x180084ebf  jle     short loc_180084ED2
0x180084ec1  mov     r9d, [rdi+58h]; unsigned int
0x180084ec5  dec     r8d; int
0x180084ec8  xor     edx, edx; int
0x180084eca  mov     rcx, rdi; this
0x180084ecd  call    ?_ResetBkColor@CImageList@@QEAAXHHK@Z; CImageList::_ResetBkColor(int,int,ulong)
0x180084ed2  lea     rcx, g_csDll; lpCriticalSection
0x180084ed9  call    cs:__imp_LeaveCriticalSection
0x180084edf  mov     eax, esi
0x180084ee1  mov     rbx, [rsp+28h+arg_0]
0x180084ee6  mov     rsi, [rsp+28h+arg_8]
0x180084eeb  add     rsp, 20h
0x180084eef  pop     rdi
0x180084ef0  retn
```
