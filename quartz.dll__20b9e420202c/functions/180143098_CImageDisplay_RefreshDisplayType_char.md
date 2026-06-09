# CImageDisplay::RefreshDisplayType(char *)

- ea: `0x180143098`
- end: `0x180143200`
- name: `?RefreshDisplayType@CImageDisplay@@QEAAJPEAD@Z`
- size: `360`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, PCNZCH lpString1)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009c2cc`
- `0x18009ddf0`
- `0x180141f68`

## callees

- `0x18002dad4`
- `0x180039250`
- `0x180143098`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x1801430fe`
- `KERNEL32!CompareStringA` at `0x1801430fe`
- `KERNEL32!LeaveCriticalSection` at `0x1801431e4`
- `KERNEL32!LeaveCriticalSection` at `0x1801431e4`
- `KERNEL32!EnterCriticalSection` at `0x1801430ab`
- `KERNEL32!EnterCriticalSection` at `0x1801430ab`
- `GDI32!DeleteObject` at `0x1801431bb`
- `GDI32!DeleteObject` at `0x1801431bb`
- `GDI32!DeleteDC` at `0x1801431ca`
- `GDI32!DeleteDC` at `0x1801431ca`
- `GDI32!GetDIBits` at `0x18014317e`
- `GDI32!GetDIBits` at `0x1801431ac`
- `GDI32!GetDIBits` at `0x18014317e`
- `GDI32!GetDIBits` at `0x1801431ac`
- `GDI32!CreateCompatibleBitmap` at `0x180143148`
- `GDI32!CreateCompatibleBitmap` at `0x180143148`
- `GDI32!CreateDCA` at `0x180143121`
- `GDI32!CreateDCA` at `0x180143121`

## pseudocode

```c
__int64 __fastcall CImageDisplay::RefreshDisplayType(LPCRITICAL_SECTION lpCriticalSection, PCNZCH lpString1)
{
  const CHAR *v4; // rdx
  const CHAR *v5; // rcx
  HDC DCA; // rax
  HDC v7; // rbx
  unsigned int v8; // ebx
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v10; // rsi
  CImageDisplay *v11; // rcx

  EnterCriticalSection(lpCriticalSection);
  memset_0(&lpCriticalSection[1], 0, 0x464u);
  lpCriticalSection[2].LockCount = 40;
  if ( !lpString1 || CompareStringA(0x7Fu, 1u, lpString1, -1, "DISPLAY", -1) == 2 )
  {
    v4 = 0;
    v5 = "DISPLAY";
  }
  else
  {
    v4 = lpString1;
    v5 = 0;
  }
  DCA = CreateDCA(v5, v4, 0, 0);
  v7 = DCA;
  if ( DCA )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DCA, 1, 1);
    v10 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      GetDIBits(v7, CompatibleBitmap, 0, 1u, 0, (LPBITMAPINFO)&lpCriticalSection[2].LockCount, 0);
      GetDIBits(v7, v10, 0, 1u, 0, (LPBITMAPINFO)&lpCriticalSection[2].LockCount, 0);
      DeleteObject(v10);
    }
    DeleteDC(v7);
    CImageDisplay::UpdateFormat(v11, (struct tagVIDEOINFO *)&lpCriticalSection[1]);
    v8 = 0;
  }
  else
  {
    v8 = -2147467259;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x180143098  push    rbx
0x18014309a  push    rbp
0x18014309b  push    rsi
0x18014309c  push    rdi
0x18014309d  push    r12
0x18014309f  push    r14
0x1801430a1  sub     rsp, 48h
0x1801430a5  mov     rbx, rdx
0x1801430a8  mov     rdi, rcx
0x1801430ab  call    cs:__imp_EnterCriticalSection
0x1801430b2  nop     dword ptr [rax+rax+00h]
0x1801430b7  xor     edx, edx; Val
0x1801430b9  lea     rcx, [rdi+28h]; void *
0x1801430bd  mov     r8d, 464h; Size
0x1801430c3  call    memset_0
0x1801430c8  lea     r14, [rdi+58h]
0x1801430cc  mov     r12d, 1
0x1801430d2  mov     dword ptr [r14], 28h ; '('
0x1801430d9  lea     rsi, pwszDriver; "DISPLAY"
0x1801430e0  test    rbx, rbx
0x1801430e3  jz      short loc_180143116
0x1801430e5  or      r9d, 0FFFFFFFFh; cchCount1
0x1801430e9  lea     ecx, [r12+7Eh]; Locale
0x1801430ee  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x1801430f3  mov     r8, rbx; lpString1
0x1801430f6  mov     edx, r12d; dwCmpFlags
0x1801430f9  mov     [rsp+78h+lpString2], rsi; lpString2
0x1801430fe  call    cs:__imp_CompareStringA
0x180143105  nop     dword ptr [rax+rax+00h]
0x18014310a  cmp     eax, 2
0x18014310d  jz      short loc_180143116
0x18014310f  mov     rdx, rbx
0x180143112  xor     ecx, ecx
0x180143114  jmp     short loc_18014311B
0x180143116  xor     edx, edx; pwszDevice
0x180143118  mov     rcx, rsi; pwszDriver
0x18014311b  xor     r9d, r9d; pdm
0x18014311e  xor     r8d, r8d; pszPort
0x180143121  call    cs:__imp_CreateDCA
0x180143128  nop     dword ptr [rax+rax+00h]
0x18014312d  mov     rbx, rax
0x180143130  test    rax, rax
0x180143133  jnz     short loc_18014313F
0x180143135  mov     ebx, 80004005h
0x18014313a  jmp     loc_1801431E1
0x18014313f  mov     r8d, r12d; cy
0x180143142  mov     edx, r12d; cx
0x180143145  mov     rcx, rbx; hdc
0x180143148  call    cs:__imp_CreateCompatibleBitmap
0x18014314f  nop     dword ptr [rax+rax+00h]
0x180143154  mov     rsi, rax
0x180143157  test    rax, rax
0x18014315a  jz      short loc_1801431C7
0x18014315c  mov     [rsp+78h+usage], 0; usage
0x180143164  mov     r9d, r12d; cLines
0x180143167  mov     qword ptr [rsp+78h+cchCount2], r14; lpbmi
0x18014316c  xor     r8d, r8d; start
0x18014316f  mov     rdx, rax; hbm
0x180143172  mov     [rsp+78h+lpString2], 0; lpvBits
0x18014317b  mov     rcx, rbx; hdc
0x18014317e  call    cs:__imp_GetDIBits
0x180143185  nop     dword ptr [rax+rax+00h]
0x18014318a  mov     [rsp+78h+usage], 0; usage
0x180143192  mov     r9d, r12d; cLines
0x180143195  mov     qword ptr [rsp+78h+cchCount2], r14; lpbmi
0x18014319a  xor     r8d, r8d; start
0x18014319d  mov     rdx, rsi; hbm
0x1801431a0  mov     [rsp+78h+lpString2], 0; lpvBits
0x1801431a9  mov     rcx, rbx; hdc
0x1801431ac  call    cs:__imp_GetDIBits
0x1801431b3  nop     dword ptr [rax+rax+00h]
0x1801431b8  mov     rcx, rsi; ho
0x1801431bb  call    cs:__imp_DeleteObject
0x1801431c2  nop     dword ptr [rax+rax+00h]
0x1801431c7  mov     rcx, rbx; hdc
0x1801431ca  call    cs:__imp_DeleteDC
0x1801431d1  nop     dword ptr [rax+rax+00h]
0x1801431d6  lea     rdx, [rdi+28h]; struct tagVIDEOINFO *
0x1801431da  call    ?UpdateFormat@CImageDisplay@@QEAAJPEAUtagVIDEOINFO@@@Z; CImageDisplay::UpdateFormat(tagVIDEOINFO *)
0x1801431df  xor     ebx, ebx
0x1801431e1  mov     rcx, rdi; lpCriticalSection
0x1801431e4  call    cs:__imp_LeaveCriticalSection
0x1801431eb  nop     dword ptr [rax+rax+00h]
0x1801431f0  mov     eax, ebx
0x1801431f2  add     rsp, 48h
0x1801431f6  pop     r14
0x1801431f8  pop     r12
0x1801431fa  pop     rdi
0x1801431fb  pop     rsi
0x1801431fc  pop     rbp
0x1801431fd  pop     rbx
0x1801431fe  retn
```
