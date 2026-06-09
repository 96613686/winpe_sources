# AllocPointerSurface(_POINTER_INFO *)

- ea: `0x14002a218`
- end: `0x14002a33c`
- name: `?AllocPointerSurface@@YAHPEAU_POINTER_INFO@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct _POINTER_INFO *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002c6f0`
- `0x1400354e0`
- `0x140035df0`

## callees

- `0x14002a218`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a295`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14002a295`
- `watchdog!WdLogSingleEntry3` at `0x14002a27e`
- `watchdog!WdLogSingleEntry3` at `0x14002a2ef`
- `watchdog!WdLogSingleEntry3` at `0x14002a27e`
- `watchdog!WdLogSingleEntry3` at `0x14002a2ef`
- `WIN32K!EngLockSurface` at `0x14002a2ce`
- `WIN32K!EngLockSurface` at `0x14002a2ce`
- `WIN32K!EngCreateBitmap` at `0x14002a25d`
- `WIN32K!EngCreateBitmap` at `0x14002a25d`

## pseudocode

```c
__int64 __fastcall AllocPointerSurface(struct _POINTER_INFO *a1)
{
  __int64 v2; // rsi
  int v3; // edi
  HBITMAP Bitmap; // rax
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 result; // rax
  SURFOBJ *v8; // rax
  int v9; // edx

  if ( *((_DWORD *)a1 + 22) )
  {
    v2 = *((int *)a1 + 20);
    v3 = 2 * *((_DWORD *)a1 + 21);
    Bitmap = EngCreateBitmap((SIZEL)__PAIR64__(v3, v2), 0, 6u, 1u, 0);
    *((_QWORD *)a1 + 8) = Bitmap;
    if ( !Bitmap )
    {
      WdLogSingleEntry3(6, *((unsigned int *)a1 + 8), v2, v3);
      v5 = 6072;
LABEL_4:
      WdLogGlobalForLineNumber = v5;
      v6 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      v6[3] = gCddImageInfo;
      v6[4] = (unsigned int)dword_14003E570;
      result = 0;
      v6[5] = 215857758;
      WdLogGlobalForLineNumber = v5;
      return result;
    }
    v8 = EngLockSurface((HSURF)Bitmap);
    *((_QWORD *)a1 + 7) = v8;
    if ( !v8 )
    {
      WdLogSingleEntry3(6, *((unsigned int *)a1 + 8), v2, v3);
      v5 = 6080;
      goto LABEL_4;
    }
    v9 = *((_DWORD *)a1 + 20);
    *((_QWORD *)a1 + 5) = v8->pvBits;
    *((_DWORD *)a1 + 4) = *((_DWORD *)a1 + 22);
    *((_DWORD *)a1 + 6) = *((_DWORD *)a1 + 21);
    *((_DWORD *)a1 + 7) = 4 * v9;
    *((_DWORD *)a1 + 5) = v9;
  }
  return 1;
}

```

## disassembly

```asm
0x14002a218  mov     [rsp+arg_8], rbx
0x14002a21d  mov     [rsp+arg_10], rsi
0x14002a222  push    rdi
0x14002a223  sub     rsp, 30h
0x14002a227  cmp     dword ptr [rcx+58h], 0
0x14002a22b  mov     rbx, rcx
0x14002a22e  jz      loc_14002A326
0x14002a234  mov     edi, [rcx+54h]
0x14002a237  xor     edx, edx; lWidth
0x14002a239  movsxd  rsi, dword ptr [rcx+50h]
0x14002a23d  add     edi, edi
0x14002a23f  mov     [rsp+38h+sizl.cy], edi
0x14002a243  mov     [rsp+38h+sizl.cx], esi
0x14002a247  mov     rcx, qword ptr [rsp+38h+sizl.cx]; sizl
0x14002a24c  lea     r9d, [rdx+1]; fl
0x14002a250  lea     r8d, [rdx+6]; iFormat
0x14002a254  mov     [rsp+38h+pvBits], 0; pvBits
0x14002a25d  call    cs:__imp_EngCreateBitmap
0x14002a264  nop     dword ptr [rax+rax+00h]
0x14002a269  mov     [rbx+40h], rax
0x14002a26d  test    rax, rax
0x14002a270  jnz     short loc_14002A2CB
0x14002a272  mov     edx, [rbx+20h]
0x14002a275  lea     ecx, [rax+6]
0x14002a278  movsxd  r9, edi
0x14002a27b  mov     r8, rsi
0x14002a27e  call    cs:__imp_WdLogSingleEntry3
0x14002a285  nop     dword ptr [rax+rax+00h]
0x14002a28a  mov     ebx, 17B8h
0x14002a28f  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a295  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14002a29c  nop     dword ptr [rax+rax+00h]
0x14002a2a1  mov     rcx, rax
0x14002a2a4  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002a2ab  mov     [rcx+18h], rax
0x14002a2af  mov     eax, cs:dword_14003E570
0x14002a2b5  mov     [rcx+20h], rax
0x14002a2b9  xor     eax, eax
0x14002a2bb  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x14002a2c3  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002a2c9  jmp     short loc_14002A32B
0x14002a2cb  mov     rcx, rax; hsurf
0x14002a2ce  call    cs:__imp_EngLockSurface
0x14002a2d5  nop     dword ptr [rax+rax+00h]
0x14002a2da  mov     [rbx+38h], rax
0x14002a2de  test    rax, rax
0x14002a2e1  jnz     short loc_14002A302
0x14002a2e3  mov     edx, [rbx+20h]
0x14002a2e6  lea     ecx, [rax+6]
0x14002a2e9  movsxd  r9, edi
0x14002a2ec  mov     r8, rsi
0x14002a2ef  call    cs:__imp_WdLogSingleEntry3
0x14002a2f6  nop     dword ptr [rax+rax+00h]
0x14002a2fb  mov     ebx, 17C0h
0x14002a300  jmp     short loc_14002A28F
0x14002a302  mov     rcx, [rax+30h]
0x14002a306  mov     edx, [rbx+50h]
0x14002a309  mov     [rbx+28h], rcx
0x14002a30d  mov     ecx, [rbx+58h]
0x14002a310  mov     [rbx+10h], ecx
0x14002a313  mov     ecx, [rbx+54h]
0x14002a316  mov     [rbx+18h], ecx
0x14002a319  lea     ecx, ds:0[rdx*4]
0x14002a320  mov     [rbx+1Ch], ecx
0x14002a323  mov     [rbx+14h], edx
0x14002a326  mov     eax, 1
0x14002a32b  mov     rbx, [rsp+38h+arg_8]
0x14002a330  mov     rsi, [rsp+38h+arg_10]
0x14002a335  add     rsp, 30h
0x14002a339  pop     rdi
0x14002a33a  retn
```
