# CddBitmapSw::CreateGDIObjects(CDDPDEV *)

- ea: `0x1400316f4`
- end: `0x14003180f`
- name: `?CreateGDIObjects@CddBitmapSw@@IEAAJPEAUCDDPDEV@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CddBitmapSw *__hidden this, struct CDDPDEV *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400319f0`

## callees

- `0x1400316f4`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdError` at `0x1400317b8`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400317b8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140031729`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140031729`
- `watchdog!WdLogSingleEntry0` at `0x140031713`
- `watchdog!WdLogSingleEntry0` at `0x1400317a1`
- `watchdog!WdLogSingleEntry0` at `0x140031713`
- `watchdog!WdLogSingleEntry0` at `0x1400317a1`
- `WIN32K!EngCreateBitmap` at `0x140031786`
- `WIN32K!EngCreateBitmap` at `0x140031786`

## pseudocode

```c
__int64 __fastcall CddBitmapSw::CreateGDIObjects(CddBitmapSw *this, struct CDDPDEV *a2)
{
  _QWORD *v4; // rax
  HBITMAP Bitmap; // rax
  _QWORD *v6; // rax
  __int64 result; // rax

  if ( !*((_QWORD *)this + 116) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 160;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 160;
  }
  Bitmap = EngCreateBitmap(*(SIZEL *)((char *)this + 16), *((_DWORD *)this + 6), 6u, 1u, (PVOID)0xDEADBEEFLL);
  *((_QWORD *)this + 117) = Bitmap;
  if ( Bitmap )
    return (*(__int64 (__fastcall **)(CddBitmapSw *, struct CDDPDEV *))(*(_QWORD *)this + 184LL))(this, a2);
  WdLogSingleEntry0(2);
  WdLogGlobalForLineNumber = 165;
  v6 = (_QWORD *)WdLogNewEntry5_WdError();
  v6[3] = gCddImageInfo;
  v6[4] = (unsigned int)dword_14003E570;
  v6[5] = 215857758;
  result = 3221225495LL;
  WdLogGlobalForLineNumber = 165;
  return result;
}

```

## disassembly

```asm
0x1400316f4  mov     [rsp+arg_8], rbx
0x1400316f9  push    rdi
0x1400316fa  sub     rsp, 30h
0x1400316fe  cmp     qword ptr [rcx+3A0h], 0
0x140031706  mov     rdi, rdx
0x140031709  mov     rbx, rcx
0x14003170c  jnz     short loc_14003175C
0x14003170e  mov     ecx, 1
0x140031713  call    cs:__imp_WdLogSingleEntry0
0x14003171a  nop     dword ptr [rax+rax+00h]
0x14003171f  mov     cs:WdLogGlobalForLineNumber, 0A0h
0x140031729  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140031730  nop     dword ptr [rax+rax+00h]
0x140031735  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14003173c  mov     [rax+18h], rcx
0x140031740  mov     ecx, cs:dword_14003E570
0x140031746  mov     [rax+20h], rcx
0x14003174a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140031752  mov     cs:WdLogGlobalForLineNumber, 0A0h
0x14003175c  mov     eax, [rbx+10h]
0x14003175f  mov     r9d, 1; fl
0x140031765  mov     edx, [rbx+18h]; lWidth
0x140031768  mov     [rsp+38h+sizl.cx], eax
0x14003176c  mov     eax, [rbx+14h]
0x14003176f  mov     [rsp+38h+sizl.cy], eax
0x140031773  lea     r8d, [r9+5]; iFormat
0x140031777  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x14003177c  mov     eax, 0DEADBEEFh
0x140031781  mov     [rsp+38h+pvBits], rax; pvBits
0x140031786  call    cs:__imp_EngCreateBitmap
0x14003178d  nop     dword ptr [rax+rax+00h]
0x140031792  mov     [rbx+3A8h], rax
0x140031799  test    rax, rax
0x14003179c  jnz     short loc_1400317EE
0x14003179e  lea     ecx, [rax+2]
0x1400317a1  call    cs:__imp_WdLogSingleEntry0
0x1400317a8  nop     dword ptr [rax+rax+00h]
0x1400317ad  mov     ebx, 0A5h
0x1400317b2  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400317b8  call    cs:__imp_WdLogNewEntry5_WdError
0x1400317bf  nop     dword ptr [rax+rax+00h]
0x1400317c4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400317cb  mov     [rax+18h], rcx
0x1400317cf  mov     ecx, cs:dword_14003E570
0x1400317d5  mov     [rax+20h], rcx
0x1400317d9  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400317e1  mov     eax, 0C0000017h
0x1400317e6  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400317ec  jmp     short loc_140031803
0x1400317ee  mov     rax, [rbx]
0x1400317f1  mov     rdx, rdi
0x1400317f4  mov     rcx, rbx
0x1400317f7  mov     rax, [rax+0B8h]
0x1400317fe  call    _guard_dispatch_icall
0x140031803  mov     rbx, [rsp+38h+arg_8]
0x140031808  add     rsp, 30h
0x14003180c  pop     rdi
0x14003180d  retn
```
