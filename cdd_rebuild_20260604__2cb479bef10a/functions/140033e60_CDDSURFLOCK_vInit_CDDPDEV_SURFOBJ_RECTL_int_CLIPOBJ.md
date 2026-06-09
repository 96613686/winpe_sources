# CDDSURFLOCK::vInit(CDDPDEV *,_SURFOBJ * *,_RECTL *,int *,_CLIPOBJ *)

- ea: `0x140033e60`
- end: `0x140033f3c`
- name: `?vInit@CDDSURFLOCK@@QEAAXPEAUCDDPDEV@@PEAPEAU_SURFOBJ@@PEAU_RECTL@@PEAHPEAU_CLIPOBJ@@@Z`
- size: `220`
- prototype: `void __usercall(CDDSURFLOCK *__hidden this@<rcx>, struct CDDPDEV *@<rdx>, struct _SURFOBJ **@<r8>, struct _RECTL *@<r9>, int *, struct _CLIPOBJ *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x14000c1cc`
- `0x1400224a0`
- `0x140033e60`
- `0x140033fcc`
- `0x1400372d0`

## import_xrefs

- `WIN32K!EngAcquireSemaphore` at `0x140033ea3`
- `WIN32K!EngAcquireSemaphore` at `0x140033ea3`

## pseudocode

```c
void __fastcall CDDSURFLOCK::vInit(
        CDDSURFLOCK *this,
        struct CDDPDEV *a2,
        struct _SURFOBJ **a3,
        struct _RECTL *a4,
        int *a5,
        struct _CLIPOBJ *a6)
{
  __int64 *v8; // rcx
  __int16 v9; // ax
  __int64 v10; // rcx
  CddBitmap *v11; // rbx
  __int64 v12; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v8 = (__int64 *)*a3;
  *a5 = 0;
  v9 = *((_WORD *)v8 + 38);
  if ( v9 == 3 )
  {
    *(_QWORD *)this = v8;
    v10 = *v8;
    *((_QWORD *)this + 1) = v10;
    EngAcquireSemaphore(*(HSEMAPHORE *)(v10 + 192));
    v11 = (CddBitmap *)*((_QWORD *)this + 1);
    if ( *((_BYTE *)v11 + 133) )
    {
      (*(void (__fastcall **)(CddBitmap *))(*(_QWORD *)v11 + 176LL))(v11);
      *((_BYTE *)v11 + 133) = 0;
      CddBitmap::LogGDIContentAfterDX(v11);
    }
    *((_BYTE *)v11 + 132) = 1;
    *((_BYTE *)v11 + 134) = 1;
  }
  else
  {
    if ( v9 != 1 )
    {
      DbgLog("CDDSURFLOCK: STYPE_BITMAP\n", a2, a3, a4);
      __debugbreak();
    }
    *((_QWORD *)this + 2) = a2;
    CDDSURFLOCK::vLockShadow(this, a4, a6);
    v12 = *((_QWORD *)this + 2);
    *a5 = 1;
    *a3 = *(struct _SURFOBJ **)(v12 + 2792);
  }
}

```

## disassembly

```asm
0x140033e60  push    rbx
0x140033e62  push    rsi
0x140033e63  push    rdi
0x140033e64  push    r14
0x140033e66  sub     rsp, 28h
0x140033e6a  mov     r14, [rsp+48h+arg_20]
0x140033e6f  xor     edi, edi
0x140033e71  mov     [rcx], rdi
0x140033e74  mov     rbx, rcx
0x140033e77  mov     [rcx+8], rdi
0x140033e7b  mov     rsi, r8
0x140033e7e  mov     [rcx+10h], rdi
0x140033e82  mov     rcx, [r8]
0x140033e85  mov     [r14], edi
0x140033e88  movzx   eax, word ptr [rcx+4Ch]
0x140033e8c  cmp     ax, 3
0x140033e90  jnz     short loc_140033EF3
0x140033e92  mov     [rbx], rcx
0x140033e95  mov     rcx, [rcx]
0x140033e98  mov     [rbx+8], rcx
0x140033e9c  mov     rcx, [rcx+0C0h]; hsem
0x140033ea3  call    cs:__imp_EngAcquireSemaphore
0x140033eaa  nop     dword ptr [rax+rax+00h]
0x140033eaf  mov     rbx, [rbx+8]
0x140033eb3  mov     al, [rbx+85h]
0x140033eb9  test    al, al
0x140033ebb  jz      short loc_140033EDE
0x140033ebd  mov     rax, [rbx]
0x140033ec0  mov     rcx, rbx
0x140033ec3  mov     rax, [rax+0B0h]
0x140033eca  call    _guard_dispatch_icall
0x140033ecf  mov     rcx, rbx; this
0x140033ed2  mov     [rbx+85h], dil
0x140033ed9  call    ?LogGDIContentAfterDX@CddBitmap@@QEAAXXZ; CddBitmap::LogGDIContentAfterDX(void)
0x140033ede  mov     edi, 1
0x140033ee3  mov     [rbx+84h], dil
0x140033eea  mov     [rbx+86h], dil
0x140033ef1  jmp     short loc_140033F31
0x140033ef3  mov     edi, 1
0x140033ef8  cmp     ax, di
0x140033efb  jnz     short loc_140033F24
0x140033efd  mov     r8, [rsp+48h+arg_28]; struct _CLIPOBJ *
0x140033f02  mov     rcx, rbx; this
0x140033f05  mov     [rbx+10h], rdx
0x140033f09  mov     rdx, r9; struct _RECTL *
0x140033f0c  call    ?vLockShadow@CDDSURFLOCK@@QEAAXPEAU_RECTL@@PEAU_CLIPOBJ@@@Z; CDDSURFLOCK::vLockShadow(_RECTL *,_CLIPOBJ *)
0x140033f11  mov     rax, [rbx+10h]
0x140033f15  mov     [r14], edi
0x140033f18  mov     rcx, [rax+0AE8h]
0x140033f1f  mov     [rsi], rcx
0x140033f22  jmp     short loc_140033F31
0x140033f24  lea     rcx, aCddsurflockSty; "CDDSURFLOCK: STYPE_BITMAP\n"
0x140033f2b  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140033f30  int     3; Trap to Debugger
0x140033f31  add     rsp, 28h
0x140033f35  pop     r14
0x140033f37  pop     rdi
0x140033f38  pop     rsi
0x140033f39  pop     rbx
0x140033f3a  retn
```
