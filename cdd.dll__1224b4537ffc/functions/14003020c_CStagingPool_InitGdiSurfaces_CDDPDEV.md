# CStagingPool::InitGdiSurfaces(CDDPDEV *)

- ea: `0x14003020c`
- end: `0x14003042d`
- name: `?InitGdiSurfaces@CStagingPool@@QEAAJPEAUCDDPDEV@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(CStagingPool *__hidden this, struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d980`

## callees

- `0x14003020c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140030232`
- `ntoskrnl!ExAllocatePool2` at `0x1400303b5`
- `ntoskrnl!ExAllocatePool2` at `0x140030232`
- `ntoskrnl!ExAllocatePool2` at `0x1400303b5`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400302a8`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400303f6`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400302a8`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400303f6`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140030264`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140030264`
- `watchdog!WdLogSingleEntry2` at `0x1400303d7`
- `watchdog!WdLogSingleEntry2` at `0x1400303d7`
- `watchdog!WdLogNewEntry5_WdError` at `0x140030396`
- `watchdog!WdLogNewEntry5_WdError` at `0x140030396`
- `watchdog!WdLogSingleEntry0` at `0x14003024d`
- `watchdog!WdLogSingleEntry0` at `0x140030367`
- `watchdog!WdLogSingleEntry0` at `0x14003037f`
- `watchdog!WdLogSingleEntry0` at `0x14003024d`
- `watchdog!WdLogSingleEntry0` at `0x140030367`
- `watchdog!WdLogSingleEntry0` at `0x14003037f`
- `WIN32K!EngLockSurface` at `0x140030319`
- `WIN32K!EngLockSurface` at `0x140030319`
- `WIN32K!EngCreateBitmap` at `0x1400302f9`
- `WIN32K!EngCreateBitmap` at `0x1400302f9`

## pseudocode

```c
__int64 __fastcall CStagingPool::InitGdiSurfaces(CStagingPool *this, struct CDDPDEV *a2)
{
  struct _KSEMAPHORE *Pool2; // rax
  int v5; // ebx
  _QWORD *v6; // rax
  __int64 result; // rax
  char *v8; // rdi
  __int64 v9; // rsi
  HBITMAP Bitmap; // rax
  __int64 v11; // r14
  SURFOBJ *v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  struct _KSEMAPHORE *v15; // rax

  Pool2 = (struct _KSEMAPHORE *)ExAllocatePool2(64, 32, 1684300612);
  *((_QWORD *)this + 101) = Pool2;
  if ( Pool2 )
  {
    KeInitializeSemaphore(Pool2, 16, 16);
    v8 = (char *)this + 792;
    *((_QWORD *)this + 100) = (char *)this + 792;
    v9 = 0;
    *((_QWORD *)this + 99) = (char *)this + 792;
    while ( (unsigned int)v9 < 0x10 )
    {
      Bitmap = EngCreateBitmap((SIZEL)0x100000001LL, 4, 6u, 1u, (PVOID)0xDEADBEEFLL);
      v11 = 5 * v9;
      *((_QWORD *)this + 5 * v9 + 22) = Bitmap;
      if ( !Bitmap )
      {
        WdLogSingleEntry0(2);
        v5 = 1242;
        goto LABEL_14;
      }
      v12 = EngLockSurface((HSURF)Bitmap);
      *((_QWORD *)this + 5 * v9 + 21) = v12;
      if ( !v12 )
      {
        WdLogSingleEntry0(2);
        v5 = 1249;
LABEL_14:
        WdLogGlobalForLineNumber = v5;
        v6 = (_QWORD *)WdLogNewEntry5_WdError();
        goto LABEL_4;
      }
      v13 = *(_QWORD *)v8;
      if ( *(char **)(*(_QWORD *)v8 + 8LL) != v8 )
        __fastfail(3u);
      v9 = (unsigned int)(v9 + 1);
      v14 = (_QWORD *)((char *)this + 8 * v11 + 152);
      *v14 = v13;
      v14[1] = v8;
      *(_QWORD *)(v13 + 8) = v14;
      *(_QWORD *)v8 = v14;
    }
    v15 = (struct _KSEMAPHORE *)ExAllocatePool2(64, 32, 1684300612);
    *((_QWORD *)this + 7) = v15;
    if ( v15 )
    {
      KeInitializeSemaphore(v15, *((_DWORD *)this + 12), *((_DWORD *)this + 12));
      result = 0;
      *((_DWORD *)this + 33) = 0;
      *((_QWORD *)this + 17) = 0;
      return result;
    }
    WdLogSingleEntry2(6, a2, *((unsigned int *)a2 + 196));
    v5 = 1259;
  }
  else
  {
    WdLogSingleEntry0(6);
    v5 = 1227;
  }
  WdLogGlobalForLineNumber = v5;
  v6 = (_QWORD *)WdLogNewEntry5_WdLowResource();
LABEL_4:
  v6[3] = gCddImageInfo;
  v6[4] = (unsigned int)dword_14003E570;
  v6[5] = 215857758;
  result = 3221225495LL;
  WdLogGlobalForLineNumber = v5;
  return result;
}

```

## disassembly

```asm
0x14003020c  mov     [rsp+arg_8], rbx
0x140030211  mov     [rsp+arg_10], rbp
0x140030216  push    rsi
0x140030217  push    rdi
0x140030218  push    r14
0x14003021a  sub     rsp, 30h
0x14003021e  mov     rbp, rdx
0x140030221  mov     rbx, rcx
0x140030224  mov     edx, 20h ; ' '
0x140030229  mov     r8d, 64646344h
0x14003022f  lea     ecx, [rdx+20h]
0x140030232  call    cs:__imp_ExAllocatePool2
0x140030239  nop     dword ptr [rax+rax+00h]
0x14003023e  mov     [rbx+328h], rax
0x140030245  test    rax, rax
0x140030248  jnz     short loc_14003029D
0x14003024a  lea     ecx, [rax+6]
0x14003024d  call    cs:__imp_WdLogSingleEntry0
0x140030254  nop     dword ptr [rax+rax+00h]
0x140030259  mov     ebx, 4CBh
0x14003025e  mov     cs:WdLogGlobalForLineNumber, ebx
0x140030264  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14003026b  nop     dword ptr [rax+rax+00h]
0x140030270  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140030277  mov     [rax+18h], rcx
0x14003027b  mov     ecx, cs:dword_14003E570
0x140030281  mov     [rax+20h], rcx
0x140030285  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14003028d  mov     eax, 0C0000017h
0x140030292  mov     cs:WdLogGlobalForLineNumber, ebx
0x140030298  jmp     loc_140030419
0x14003029d  mov     edx, 10h; Count
0x1400302a2  mov     rcx, rax; Semaphore
0x1400302a5  mov     r8d, edx; Limit
0x1400302a8  call    cs:__imp_KeInitializeSemaphore
0x1400302af  nop     dword ptr [rax+rax+00h]
0x1400302b4  lea     rdi, [rbx+318h]
0x1400302bb  mov     [rsp+48h+sizl.cx], 1
0x1400302c3  mov     [rdi+8], rdi
0x1400302c7  xor     esi, esi
0x1400302c9  mov     [rdi], rdi
0x1400302cc  mov     [rsp+48h+sizl.cy], 1
0x1400302d4  cmp     esi, 10h
0x1400302d7  jnb     loc_1400303A7
0x1400302dd  mov     rcx, qword ptr [rsp+48h+sizl.cx]; sizl
0x1400302e2  mov     edx, 4; lWidth
0x1400302e7  mov     eax, 0DEADBEEFh
0x1400302ec  mov     [rsp+48h+pvBits], rax; pvBits
0x1400302f1  lea     r9d, [rdx-3]; fl
0x1400302f5  lea     r8d, [rdx+2]; iFormat
0x1400302f9  call    cs:__imp_EngCreateBitmap
0x140030300  nop     dword ptr [rax+rax+00h]
0x140030305  lea     r14, [rsi+rsi*4]
0x140030309  mov     [rbx+r14*8+0B0h], rax
0x140030311  test    rax, rax
0x140030314  jz      short loc_14003037A
0x140030316  mov     rcx, rax; hsurf
0x140030319  call    cs:__imp_EngLockSurface
0x140030320  nop     dword ptr [rax+rax+00h]
0x140030325  mov     [rbx+r14*8+0A8h], rax
0x14003032d  test    rax, rax
0x140030330  jz      short loc_140030362
0x140030332  mov     rcx, [rdi]
0x140030335  cmp     [rcx+8], rdi
0x140030339  jnz     short loc_14003035B
0x14003033b  lea     rax, [rbx+98h]
0x140030342  inc     esi
0x140030344  lea     rax, [rax+r14*8]
0x140030348  mov     [rax], rcx
0x14003034b  mov     [rax+8], rdi
0x14003034f  mov     [rcx+8], rax
0x140030353  mov     [rdi], rax
0x140030356  jmp     loc_1400302D4
0x14003035b  mov     ecx, 3
0x140030360  int     29h; Win8: RtlFailFast(ecx)
0x140030362  mov     ecx, 2
0x140030367  call    cs:__imp_WdLogSingleEntry0
0x14003036e  nop     dword ptr [rax+rax+00h]
0x140030373  mov     ebx, 4E1h
0x140030378  jmp     short loc_140030390
0x14003037a  mov     ecx, 2
0x14003037f  call    cs:__imp_WdLogSingleEntry0
0x140030386  nop     dword ptr [rax+rax+00h]
0x14003038b  mov     ebx, 4DAh
0x140030390  mov     cs:WdLogGlobalForLineNumber, ebx
0x140030396  call    cs:__imp_WdLogNewEntry5_WdError
0x14003039d  nop     dword ptr [rax+rax+00h]
0x1400303a2  jmp     loc_140030270
0x1400303a7  mov     edx, 20h ; ' '
0x1400303ac  mov     r8d, 64646344h
0x1400303b2  lea     ecx, [rdx+20h]
0x1400303b5  call    cs:__imp_ExAllocatePool2
0x1400303bc  nop     dword ptr [rax+rax+00h]
0x1400303c1  mov     [rbx+38h], rax
0x1400303c5  test    rax, rax
0x1400303c8  jnz     short loc_1400303ED
0x1400303ca  mov     r8d, [rbp+310h]
0x1400303d1  lea     ecx, [rax+6]
0x1400303d4  mov     rdx, rbp
0x1400303d7  call    cs:__imp_WdLogSingleEntry2
0x1400303de  nop     dword ptr [rax+rax+00h]
0x1400303e3  mov     ebx, 4EBh
0x1400303e8  jmp     loc_14003025E
0x1400303ed  mov     edx, [rbx+30h]; Count
0x1400303f0  mov     rcx, rax; Semaphore
0x1400303f3  mov     r8d, edx; Limit
0x1400303f6  call    cs:__imp_KeInitializeSemaphore
0x1400303fd  nop     dword ptr [rax+rax+00h]
0x140030402  xor     eax, eax
0x140030404  mov     dword ptr [rbx+84h], 0
0x14003040e  mov     qword ptr [rbx+88h], 0
0x140030419  mov     rbx, [rsp+48h+arg_8]
0x14003041e  mov     rbp, [rsp+48h+arg_10]
0x140030423  add     rsp, 30h
0x140030427  pop     r14
0x140030429  pop     rdi
0x14003042a  pop     rsi
0x14003042b  retn
```
