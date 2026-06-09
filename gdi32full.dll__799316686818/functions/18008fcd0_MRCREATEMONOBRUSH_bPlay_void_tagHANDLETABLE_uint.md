# MRCREATEMONOBRUSH::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x18008fcd0`
- end: `0x18008fde3`
- name: `?bPlay@MRCREATEMONOBRUSH@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `275`
- prototype: `__int64 __fastcall(MRCREATEMONOBRUSH *__hidden this, void *, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800305e0`

## callees

- `0x18001eb5c`
- `0x18005fa30`
- `0x180078300`
- `0x1800785d4`
- `0x18008fcd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fd91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fdcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fd91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008fdcd`
- `GDI32!DeleteObject` at `0x18008fdac`
- `GDI32!DeleteObject` at `0x18008fdac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall MRCREATEMONOBRUSH::bPlay(
        MRCREATEMONOBRUSH *this,
        void *a2,
        struct tagHANDLETABLE *a3,
        unsigned int a4)
{
  HLOCAL v7; // rcx
  HLOCAL v8; // rdi
  HBITMAP MonoDib; // rax
  HBITMAP v10; // rbp
  BOOL v11; // ebx
  HLOCAL hMem; // [rsp+50h] [rbp-38h] BYREF
  char v14; // [rsp+58h] [rbp-30h]

  hMem = 0;
  v14 = 0;
  if ( !(unsigned int)MRBRUSH::bCheckRecord(this, a3) || *((_DWORD *)this + 2) >= a4 || !*((_DWORD *)this + 2) )
    return 0;
  if ( !(unsigned int)bCheckBitmap(
                        a3,
                        this,
                        *((_DWORD *)this + 4),
                        *((_DWORD *)this + 5),
                        *((_DWORD *)this + 6),
                        *((_DWORD *)this + 7),
                        *((_DWORD *)this + 3),
                        0,
                        (BitmapInfoPtr *)&hMem) )
  {
    v7 = hMem;
    if ( !hMem || !v14 )
      return 0;
    goto LABEL_12;
  }
  v8 = hMem;
  MonoDib = (HBITMAP)CreateMonoDib(
                       (BITMAPINFO *)hMem,
                       (char *)this + *((unsigned int *)this + 6),
                       *((_DWORD *)this + 3));
  v10 = MonoDib;
  if ( !MonoDib )
  {
    if ( !v8 || !v14 )
      return 0;
    v7 = v8;
LABEL_12:
    LocalFree(v7);
    return 0;
  }
  a3[*((unsigned int *)this + 2)].objectHandle[0] = CreatePatternBrush(MonoDib);
  DeleteObject(v10);
  v11 = a3[*((unsigned int *)this + 2)].objectHandle[0] != 0;
  if ( v8 && v14 )
    LocalFree(v8);
  return v11;
}

```

## disassembly

```asm
0x18008fcd0  push    rbx
0x18008fcd2  push    rbp
0x18008fcd3  push    rsi
0x18008fcd4  push    rdi
0x18008fcd5  sub     rsp, 68h
0x18008fcd9  mov     edi, r9d
0x18008fcdc  mov     rsi, r8
0x18008fcdf  mov     rbx, rcx
0x18008fce2  mov     [rsp+88h+hMem], 0
0x18008fceb  mov     [rsp+88h+var_30], 0
0x18008fcf0  mov     rdx, r8; struct tagHANDLETABLE *
0x18008fcf3  call    ?bCheckRecord@MRBRUSH@@QEAAHPEAUtagHANDLETABLE@@@Z; MRBRUSH::bCheckRecord(tagHANDLETABLE *)
0x18008fcf8  test    eax, eax
0x18008fcfa  jnz     short loc_18008FD01
0x18008fcfc  jmp     loc_18008FDD8
0x18008fd01  cmp     [rbx+8], edi
0x18008fd04  jnb     loc_18008FDD8
0x18008fd0a  cmp     dword ptr [rbx+8], 0
0x18008fd0e  jz      loc_18008FDD8
0x18008fd14  lea     rax, [rsp+88h+hMem]
0x18008fd19  mov     [rsp+88h+var_48], rax; BitmapInfoPtr *
0x18008fd1e  mov     [rsp+88h+var_50], 0; int
0x18008fd26  mov     eax, [rbx+0Ch]
0x18008fd29  mov     [rsp+88h+var_58], eax; int
0x18008fd2d  mov     eax, [rbx+1Ch]
0x18008fd30  mov     [rsp+88h+var_60], eax; int
0x18008fd34  mov     eax, [rbx+18h]
0x18008fd37  mov     [rsp+88h+var_68], eax; int
0x18008fd3b  mov     r9d, [rbx+14h]
0x18008fd3f  mov     r8d, [rbx+10h]
0x18008fd43  mov     rdx, rbx; this
0x18008fd46  mov     rcx, rsi; struct tagHANDLETABLE *
0x18008fd49  call    bCheckBitmap
0x18008fd4e  test    eax, eax
0x18008fd50  jnz     short loc_18008FD64
0x18008fd52  mov     rcx, [rsp+88h+hMem]
0x18008fd57  test    rcx, rcx
0x18008fd5a  jz      short loc_18008FD98
0x18008fd5c  cmp     [rsp+88h+var_30], al
0x18008fd60  jz      short loc_18008FD98
0x18008fd62  jmp     short loc_18008FD91
0x18008fd64  mov     edx, [rbx+18h]
0x18008fd67  add     rdx, rbx; lpBits
0x18008fd6a  mov     r8d, [rbx+0Ch]; ColorUse
0x18008fd6e  mov     rdi, [rsp+88h+hMem]
0x18008fd73  mov     rcx, rdi; lpbmi
0x18008fd76  call    CreateMonoDib
0x18008fd7b  mov     rbp, rax
0x18008fd7e  test    rax, rax
0x18008fd81  jnz     short loc_18008FD9A
0x18008fd83  test    rdi, rdi
0x18008fd86  jz      short loc_18008FD98
0x18008fd88  cmp     [rsp+88h+var_30], al
0x18008fd8c  jz      short loc_18008FD98
0x18008fd8e  mov     rcx, rdi; hMem
0x18008fd91  call    cs:__imp_LocalFree
0x18008fd97  nop
0x18008fd98  jmp     short loc_18008FDD8
0x18008fd9a  mov     rcx, rbp; hbm
0x18008fd9d  call    CreatePatternBrush
0x18008fda2  mov     ecx, [rbx+8]
0x18008fda5  mov     [rsi+rcx*8], rax
0x18008fda9  mov     rcx, rbp; ho
0x18008fdac  call    cs:__imp_DeleteObject
0x18008fdb2  mov     eax, [rbx+8]
0x18008fdb5  xor     ebx, ebx
0x18008fdb7  cmp     [rsi+rax*8], rbx
0x18008fdbb  setnz   bl
0x18008fdbe  test    rdi, rdi
0x18008fdc1  jz      short loc_18008FDD4
0x18008fdc3  cmp     [rsp+88h+var_30], 0
0x18008fdc8  jz      short loc_18008FDD4
0x18008fdca  mov     rcx, rdi; hMem
0x18008fdcd  call    cs:__imp_LocalFree
0x18008fdd3  nop
0x18008fdd4  mov     eax, ebx
0x18008fdd6  jmp     short loc_18008FDDA
0x18008fdd8  xor     eax, eax
0x18008fdda  add     rsp, 68h
0x18008fdde  pop     rdi
0x18008fddf  pop     rsi
0x18008fde0  pop     rbp
0x18008fde1  pop     rbx
0x18008fde2  retn
```
