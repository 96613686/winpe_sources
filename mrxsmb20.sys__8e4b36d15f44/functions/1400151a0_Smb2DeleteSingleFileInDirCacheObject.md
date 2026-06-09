# Smb2DeleteSingleFileInDirCacheObject

- ea: `0x1400151a0`
- end: `0x14001534f`
- name: `Smb2DeleteSingleFileInDirCacheObject`
- size: `431`
- prototype: `__int64 __fastcall(void *Context, PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014db0`

## callees

- `0x140004f20`
- `0x1400151a0`
- `0x14003504c`
- `0x1400355c8`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x14001528a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400152ee`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001533b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001528a`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400152ee`
- `ntoskrnl!ExReleasePushLockEx` at `0x14001533b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001524e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14001524e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400152cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001531f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400152cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001531f`

## pseudocode

```c
__int64 __fastcall Smb2DeleteSingleFileInDirCacheObject(
        volatile signed __int32 *Context,
        PCUNICODE_STRING String1,
        __int64 a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 *v7; // rsi
  char *v8; // rbp
  int v9; // r14d
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  result = *((unsigned int *)Context + 8);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 3 )
    {
      ExAcquirePushLockExclusiveEx(Context + 26, 0);
      if ( *((_DWORD *)Context + 8) == 3 )
        _InterlockedIncrement(Context + 14);
      return ExReleasePushLockEx(Context + 26, 0);
    }
  }
  else
  {
    v10 = 0;
    LODWORD(v11) = 0;
    if ( !a4 )
      v10 = 0;
    v7 = &v10;
    if ( a4 )
      v7 = a4;
    if ( HIDWORD(*v7) == *((_DWORD *)Context + 10) )
    {
      if ( (int)*v7 >= 0 )
        __int2c();
      v8 = (char *)(Context + 26);
LABEL_17:
      if ( HIDWORD(*v7) == *((_DWORD *)Context + 10) )
      {
        if ( (int)*v7 >= 0 )
          __int2c();
        v8 = (char *)(Context + 26);
      }
      else
      {
        __int2c();
      }
      ExAcquirePushLockExclusiveEx(v8, 0);
      DeleteDirectoryCacheEntry(Context, v7, String1);
      return ExReleasePushLockEx(v8, 0);
    }
    *v7 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_ZqZ(WPP_GLOBAL_Control->AttachedDevice, 23, a3, (_DWORD)String1, (char)Context, a3);
    }
    v8 = (char *)(Context + 26);
    ExAcquirePushLockSharedEx(Context + 26, 0);
    v9 = QueryFileInfoFromDirectoryCache((unsigned int *)Context, String1, 1, 4u, v7, 0, &v11);
    result = ExReleasePushLockEx(Context + 26, 0);
    if ( v9 == -1073741789 || v9 == -1073741802 || v9 >= 0 )
      goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x1400151a0  mov     r11, rsp
0x1400151a3  push    rbx
0x1400151a4  push    rdi
0x1400151a5  sub     rsp, 58h
0x1400151a9  mov     eax, [rcx+20h]
0x1400151ac  mov     rdi, rdx
0x1400151af  mov     rbx, rcx
0x1400151b2  test    eax, eax
0x1400151b4  jnz     loc_140015314
0x1400151ba  mov     [r11+18h], rsi
0x1400151be  mov     [r11-18h], r14
0x1400151c2  xor     r14d, r14d
0x1400151c5  mov     [r11-28h], r14
0x1400151c9  mov     [r11+8], r14d
0x1400151cd  test    r9, r9
0x1400151d0  jnz     short loc_1400151D6
0x1400151d2  mov     [r11-28h], r14
0x1400151d6  test    r9, r9
0x1400151d9  mov     [rsp+68h+arg_8], rbp
0x1400151de  lea     rsi, [rsp+68h+var_28]
0x1400151e3  cmovnz  rsi, r9
0x1400151e7  mov     rcx, [rsi]
0x1400151ea  mov     rax, rcx
0x1400151ed  shr     rax, 20h
0x1400151f1  cmp     eax, [rbx+28h]
0x1400151f4  jnz     short loc_140015205
0x1400151f6  test    ecx, ecx
0x1400151f8  js      short loc_1400151FC
0x1400151fa  int     2Ch; Windows NT - assertion failure
0x1400151fc  lea     rbp, [rbx+68h]
0x140015200  jmp     loc_1400152AD
0x140015205  mov     [rsi], r14
0x140015208  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001520f  lea     rax, WPP_GLOBAL_Control
0x140015216  cmp     rcx, rax
0x140015219  jz      short loc_140015245
0x14001521b  test    dword ptr [rcx+2Ch], 100h
0x140015222  jz      short loc_140015245
0x140015224  cmp     byte ptr [rcx+29h], 2
0x140015228  jb      short loc_140015245
0x14001522a  mov     rcx, [rcx+18h]
0x14001522e  mov     edx, 17h
0x140015233  mov     [rsp+68h+var_40], r8
0x140015238  mov     r9, rdi
0x14001523b  mov     [rsp+68h+var_48], rbx
0x140015240  call    WPP_SF_ZqZ
0x140015245  lea     rbp, [rbx+68h]
0x140015249  xor     edx, edx
0x14001524b  mov     rcx, rbp
0x14001524e  call    cs:__imp_ExAcquirePushLockSharedEx
0x140015255  nop     dword ptr [rax+rax+00h]
0x14001525a  lea     rax, [rsp+68h+arg_0]
0x14001525f  mov     r9d, 4
0x140015265  mov     [rsp+68h+var_38], rax; __int64
0x14001526a  mov     r8b, 1
0x14001526d  mov     [rsp+68h+var_40], r14; __int64
0x140015272  mov     rdx, rdi; String1
0x140015275  mov     rcx, rbx; Context
0x140015278  mov     [rsp+68h+var_48], rsi; __int64
0x14001527d  call    QueryFileInfoFromDirectoryCache
0x140015282  xor     edx, edx
0x140015284  mov     rcx, rbp
0x140015287  mov     r14d, eax
0x14001528a  call    cs:__imp_ExReleasePushLockEx
0x140015291  nop     dword ptr [rax+rax+00h]
0x140015296  cmp     r14d, 0C0000023h
0x14001529d  jz      short loc_1400152AD
0x14001529f  cmp     r14d, 0C0000016h
0x1400152a6  jz      short loc_1400152AD
0x1400152a8  test    r14d, r14d
0x1400152ab  js      short loc_1400152FA
0x1400152ad  mov     rcx, [rsi]
0x1400152b0  mov     rax, rcx
0x1400152b3  shr     rax, 20h
0x1400152b7  cmp     eax, [rbx+28h]
0x1400152ba  jnz     short loc_1400152C8
0x1400152bc  test    ecx, ecx
0x1400152be  js      short loc_1400152C2
0x1400152c0  int     2Ch; Windows NT - assertion failure
0x1400152c2  lea     rbp, [rbx+68h]
0x1400152c6  jmp     short loc_1400152CA
0x1400152c8  int     2Ch; Windows NT - assertion failure
0x1400152ca  xor     edx, edx
0x1400152cc  mov     rcx, rbp
0x1400152cf  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400152d6  nop     dword ptr [rax+rax+00h]
0x1400152db  mov     r8, rdi
0x1400152de  mov     rdx, rsi
0x1400152e1  mov     rcx, rbx
0x1400152e4  call    DeleteDirectoryCacheEntry
0x1400152e9  xor     edx, edx
0x1400152eb  mov     rcx, rbp
0x1400152ee  call    cs:__imp_ExReleasePushLockEx
0x1400152f5  nop     dword ptr [rax+rax+00h]
0x1400152fa  mov     rbp, [rsp+68h+arg_8]
0x1400152ff  mov     rsi, [rsp+68h+arg_10]
0x140015307  mov     r14, [rsp+68h+var_18]
0x14001530c  add     rsp, 58h
0x140015310  pop     rdi
0x140015311  pop     rbx
0x140015312  retn
0x140015314  cmp     eax, 3
0x140015317  jnz     short loc_14001530C
0x140015319  xor     edx, edx
0x14001531b  add     rcx, 68h ; 'h'
0x14001531f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140015326  nop     dword ptr [rax+rax+00h]
0x14001532b  xor     edx, edx
0x14001532d  lea     rcx, [rbx+68h]
0x140015331  cmp     dword ptr [rbx+20h], 3
0x140015335  jnz     short loc_14001533B
0x140015337  lock inc dword ptr [rbx+38h]
0x14001533b  call    cs:__imp_ExReleasePushLockEx
0x140015342  nop     dword ptr [rax+rax+00h]
0x140015347  add     rsp, 58h
0x14001534b  pop     rdi
0x14001534c  pop     rbx
0x14001534d  retn
```
