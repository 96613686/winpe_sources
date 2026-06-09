# FvepCreateTPMProtector(void *)

- ea: `0x180026040`
- end: `0x180026115`
- name: `?FvepCreateTPMProtector@@YAJPEAX@Z`
- size: `213`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002868c`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x180026040`
- `0x180028648`

## import_xrefs

- `FVEAPI!FveAddAuthMethodInformation` at `0x180026098`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180026098`

## pseudocode

```c
__int64 __fastcall FvepCreateTPMProtector(void *a1)
{
  unsigned int v1; // ebx
  const char *v3; // [rsp+28h] [rbp-60h]
  _QWORD v4[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v5; // [rsp+40h] [rbp-48h]
  __int128 v6; // [rsp+50h] [rbp-38h]
  __int64 v7; // [rsp+60h] [rbp-28h]
  __int128 v8; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4[0] = 0x100000038LL;
  v4[1] = 0x20000;
  v5 = 0;
  v7 = 0;
  v6 = 0;
  v8 = 0;
  v1 = FveAddAuthMethodInformation(a1, v4, &v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v1);
  if ( (v1 & 0x80000000) != 0 )
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x47A,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)v1,
      (int)"FveAddAuthMethodInformation",
      v3);
  return v1;
}

```

## disassembly

```asm
0x180026040  push    rbx
0x180026042  sub     rsp, 80h
0x180026049  mov     rax, cs:__security_cookie
0x180026050  xor     rax, rsp
0x180026053  mov     [rsp+88h+var_10], rax
0x180026058  xorps   xmm0, xmm0
0x18002605b  lea     r8, [rsp+88h+var_20]
0x180026060  movups  [rsp+88h+var_58], xmm0
0x180026065  xor     eax, eax
0x180026067  mov     dword ptr [rsp+88h+var_58], 38h ; '8'
0x18002606f  lea     rdx, [rsp+88h+var_58]
0x180026074  mov     dword ptr [rsp+88h+var_58+4], 1
0x18002607c  mov     dword ptr [rsp+88h+var_58+8], 20000h
0x180026084  movups  [rsp+88h+var_48], xmm0
0x180026089  mov     [rsp+88h+var_28], rax
0x18002608e  movups  [rsp+88h+var_38], xmm0
0x180026093  movups  [rsp+88h+var_20], xmm0
0x180026098  call    cs:__imp_FveAddAuthMethodInformation
0x18002609e  mov     ebx, eax
0x1800260a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260a7  lea     rax, WPP_GLOBAL_Control
0x1800260ae  cmp     rcx, rax
0x1800260b1  jz      short loc_1800260D1
0x1800260b3  test    byte ptr [rcx+1Ch], 40h
0x1800260b7  jz      short loc_1800260D1
0x1800260b9  mov     rcx, [rcx+10h]
0x1800260bd  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800260c4  mov     edx, 60h ; '`'
0x1800260c9  mov     r9d, ebx
0x1800260cc  call    WPP_SF_d
0x1800260d1  test    ebx, ebx
0x1800260d3  jns     short loc_1800260FD
0x1800260d5  mov     rcx, [rsp+88h]; this
0x1800260dd  lea     rax, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1800260e4  mov     r9d, ebx; char *
0x1800260e7  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800260ec  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x1800260f3  mov     edx, 47Ah; void *
0x1800260f8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800260fd  mov     eax, ebx
0x1800260ff  mov     rcx, [rsp+88h+var_10]
0x180026104  xor     rcx, rsp; StackCookie
0x180026107  call    __security_check_cookie
0x18002610c  add     rsp, 80h
0x180026113  pop     rbx
0x180026114  retn
```
