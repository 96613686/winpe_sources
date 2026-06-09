# MRCREATEMONOBRUSH::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180095700`
- end: `0x180095826`
- name: `?bPlay@MRCREATEMONOBRUSH@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `294`
- prototype: `__int64 __fastcall(MRCREATEMONOBRUSH *__hidden this, void *, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016350`

## callees

- `0x180034210`
- `0x180064020`
- `0x18007cdd0`
- `0x18007d0ac`
- `0x180095700`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800957c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095809`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800957c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180095809`
- `GDI32!DeleteObject` at `0x1800957e2`
- `GDI32!DeleteObject` at `0x1800957e2`

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
0x180095700  push    rbx
0x180095702  push    rbp
0x180095703  push    rsi
0x180095704  push    rdi
0x180095705  sub     rsp, 68h
0x180095709  mov     edi, r9d
0x18009570c  mov     rsi, r8
0x18009570f  mov     rbx, rcx
0x180095712  mov     [rsp+88h+hMem], 0
0x18009571b  mov     [rsp+88h+var_30], 0
0x180095720  mov     rdx, r8; struct tagHANDLETABLE *
0x180095723  call    ?bCheckRecord@MRBRUSH@@QEAAHPEAUtagHANDLETABLE@@@Z; MRBRUSH::bCheckRecord(tagHANDLETABLE *)
0x180095728  test    eax, eax
0x18009572a  jnz     short loc_180095731
0x18009572c  jmp     loc_18009581A
0x180095731  cmp     [rbx+8], edi
0x180095734  jnb     loc_18009581A
0x18009573a  cmp     dword ptr [rbx+8], 0
0x18009573e  jz      loc_18009581A
0x180095744  lea     rax, [rsp+88h+hMem]
0x180095749  mov     [rsp+88h+var_48], rax; BitmapInfoPtr *
0x18009574e  mov     [rsp+88h+var_50], 0; int
0x180095756  mov     eax, [rbx+0Ch]
0x180095759  mov     [rsp+88h+var_58], eax; int
0x18009575d  mov     eax, [rbx+1Ch]
0x180095760  mov     [rsp+88h+var_60], eax; int
0x180095764  mov     eax, [rbx+18h]
0x180095767  mov     [rsp+88h+var_68], eax; int
0x18009576b  mov     r9d, [rbx+14h]
0x18009576f  mov     r8d, [rbx+10h]
0x180095773  mov     rdx, rbx; this
0x180095776  mov     rcx, rsi; struct tagHANDLETABLE *
0x180095779  call    bCheckBitmap
0x18009577e  test    eax, eax
0x180095780  jnz     short loc_180095794
0x180095782  mov     rcx, [rsp+88h+hMem]
0x180095787  test    rcx, rcx
0x18009578a  jz      short loc_1800957CE
0x18009578c  cmp     [rsp+88h+var_30], al
0x180095790  jz      short loc_1800957CE
0x180095792  jmp     short loc_1800957C1
0x180095794  mov     edx, [rbx+18h]
0x180095797  add     rdx, rbx; lpBits
0x18009579a  mov     r8d, [rbx+0Ch]; ColorUse
0x18009579e  mov     rdi, [rsp+88h+hMem]
0x1800957a3  mov     rcx, rdi; lpbmi
0x1800957a6  call    CreateMonoDib
0x1800957ab  mov     rbp, rax
0x1800957ae  test    rax, rax
0x1800957b1  jnz     short loc_1800957D0
0x1800957b3  test    rdi, rdi
0x1800957b6  jz      short loc_1800957CE
0x1800957b8  cmp     [rsp+88h+var_30], al
0x1800957bc  jz      short loc_1800957CE
0x1800957be  mov     rcx, rdi; hMem
0x1800957c1  call    cs:__imp_LocalFree
0x1800957c8  nop     dword ptr [rax+rax+00h]
0x1800957cd  nop
0x1800957ce  jmp     short loc_18009581A
0x1800957d0  mov     rcx, rbp; hbm
0x1800957d3  call    CreatePatternBrush
0x1800957d8  mov     ecx, [rbx+8]
0x1800957db  mov     [rsi+rcx*8], rax
0x1800957df  mov     rcx, rbp; ho
0x1800957e2  call    cs:__imp_DeleteObject
0x1800957e9  nop     dword ptr [rax+rax+00h]
0x1800957ee  mov     eax, [rbx+8]
0x1800957f1  xor     ebx, ebx
0x1800957f3  cmp     [rsi+rax*8], rbx
0x1800957f7  setnz   bl
0x1800957fa  test    rdi, rdi
0x1800957fd  jz      short loc_180095816
0x1800957ff  cmp     [rsp+88h+var_30], 0
0x180095804  jz      short loc_180095816
0x180095806  mov     rcx, rdi; hMem
0x180095809  call    cs:__imp_LocalFree
0x180095810  nop     dword ptr [rax+rax+00h]
0x180095815  nop
0x180095816  mov     eax, ebx
0x180095818  jmp     short loc_18009581C
0x18009581a  xor     eax, eax
0x18009581c  add     rsp, 68h
0x180095820  pop     rdi
0x180095821  pop     rsi
0x180095822  pop     rbp
0x180095823  pop     rbx
0x180095824  retn
```
