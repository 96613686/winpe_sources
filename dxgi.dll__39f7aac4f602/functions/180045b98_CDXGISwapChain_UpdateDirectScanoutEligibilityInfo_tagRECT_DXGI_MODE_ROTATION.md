# CDXGISwapChain::UpdateDirectScanoutEligibilityInfo(tagRECT,DXGI_MODE_ROTATION)

- ea: `0x180045b98`
- end: `0x180045f8e`
- name: `?UpdateDirectScanoutEligibilityInfo@CDXGISwapChain@@IEAAXUtagRECT@@W4DXGI_MODE_ROTATION@@@Z`
- size: `1014`
- prototype: `void(CDXGISwapChain *__hidden this, struct tagRECT *__struct_ptr, enum DXGI_MODE_ROTATION)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180007b54`

## callees

- `0x18000c6b0`
- `0x180045b98`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cf2`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045c8f`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045ca0`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045d33`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045d48`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045c8f`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045ca0`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045d33`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x180045d48`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180045da4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IntersectRect` at `0x180045da4`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c2d`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c61`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c73`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045db2`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c2d`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c61`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045c73`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180045db2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x180045c4f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowInfo` at `0x180045c4f`

## string_xrefs

- `0x180045cd7`: `Invalid DisplayModeDesc and DisplayRect in UpdateFullscreenPresentInfo`
- `0x180045cfe`: `GetWindowInfo failed or returned empty rect in UpdateFullscreenPresentInfo`

## pseudocode

```c
void __fastcall CDXGISwapChain::UpdateDirectScanoutEligibilityInfo(
        CDXGISwapChain *this,
        struct tagRECT *a2,
        enum DXGI_MODE_ROTATION a3,
        bool a4)
{
  CModule *v5; // rcx
  unsigned int *v8; // rsi
  bool v9; // r14
  const char *v10; // r8
  unsigned int v11; // edx
  signed int LastError; // eax
  bool v13; // sf
  unsigned int v14; // r12d
  unsigned int v15; // r15d
  unsigned int v16; // eax
  LONG right; // r8d
  LONG bottom; // r10d
  LONG left; // r9d
  int v20; // ecx
  LONG top; // r11d
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  struct tagWINDOWINFO pwi; // [rsp+20h] [rbp-60h] BYREF
  struct tagRECT rcDst; // [rsp+60h] [rbp-20h] BYREF

  v5 = (CModule *)*((unsigned int *)this + 514);
  memset(&pwi, 0, sizeof(pwi));
  pwi.cbSize = 60;
  v8 = (unsigned int *)((char *)this + 2060);
  v9 = *((_QWORD *)this + 47) == __PAIR64__(*((_DWORD *)this + 515), (unsigned int)v5);
  if ( __PAIR64__(*((_DWORD *)this + 515), (unsigned int)v5) != __PAIR64__(a2->bottom - a2->top, a2->right - a2->left)
    || IsRectEmpty(a2)
    || a3 == DXGI_MODE_ROTATION_UNSPECIFIED )
  {
    v10 = "Invalid DisplayModeDesc and DisplayRect in UpdateFullscreenPresentInfo";
    v11 = -2147418113;
LABEL_14:
    CModule::RecordJournalImpl(v5, v11, v10, a4);
    return;
  }
  if ( GetWindowInfo(*((HWND *)this + 42), &pwi) && !IsRectEmpty(&pwi.rcWindow) && !IsRectEmpty(&pwi.rcClient) )
  {
    if ( a3 != DXGI_MODE_ROTATION_IDENTITY )
      ++*((_DWORD *)this + 1148);
    if ( !EqualRect(&pwi.rcWindow, &pwi.rcClient) || !EqualRect(&pwi.rcWindow, a2) || !v9 )
    {
      v14 = pwi.rcWindow.right - pwi.rcWindow.left;
      v15 = pwi.rcWindow.bottom - pwi.rcWindow.top;
      ++*((_DWORD *)this + 1149);
      if ( !EqualRect(&pwi.rcWindow, &pwi.rcClient) )
        ++*((_DWORD *)this + 1150);
      if ( !EqualRect(&pwi.rcWindow, a2) )
        ++*((_DWORD *)this + 1151);
      if ( v14 != *((_DWORD *)this + 94) || v15 != *((_DWORD *)this + 95) )
        ++*((_DWORD *)this + 1152);
      if ( !v9 )
        ++*((_DWORD *)this + 1153);
      if ( pwi.rcWindow.top != a2->top || pwi.rcWindow.left != a2->left )
        ++*((_DWORD *)this + 1154);
      rcDst = 0;
      if ( IntersectRect(&rcDst, &pwi.rcWindow, a2) && !IsRectEmpty(&rcDst) )
        ++*((_DWORD *)this + 1155);
      if ( v15 > *v8 )
        ++*((_DWORD *)this + 1156);
      v16 = *((_DWORD *)this + 514);
      if ( v14 > v16 )
        ++*((_DWORD *)this + 1157);
      if ( v16 != *((_DWORD *)this + 94) || *v8 != *((_DWORD *)this + 95) )
        ++*((_DWORD *)this + 1158);
      if ( *((unsigned int *)this + 516) * (unsigned __int64)*((unsigned int *)this + 97) != *((unsigned int *)this + 96)
                                                                                           * (unsigned __int64)*((unsigned int *)this + 517) )
        ++*((_DWORD *)this + 1159);
      right = pwi.rcWindow.right;
      bottom = pwi.rcWindow.bottom;
      left = pwi.rcWindow.left;
      v20 = pwi.rcWindow.right - pwi.rcWindow.left;
      top = pwi.rcWindow.top;
      v22 = pwi.rcWindow.bottom - pwi.rcWindow.top;
      if ( *((_DWORD *)this + 1170) - *((_DWORD *)this + 1168) > pwi.rcWindow.bottom - pwi.rcWindow.top
        && *((_DWORD *)this + 1169) - *((_DWORD *)this + 1167) > v20 )
      {
        *((_DWORD *)this + 1167) = pwi.rcWindow.left;
        *((_DWORD *)this + 1168) = top;
        *((_DWORD *)this + 1169) = right;
        *((_DWORD *)this + 1170) = bottom;
      }
      if ( *((_DWORD *)this + 1166) - *((_DWORD *)this + 1164) < v22
        && *((_DWORD *)this + 1165) - *((_DWORD *)this + 1163) < v20 )
      {
        *((_DWORD *)this + 1163) = left;
        *((_DWORD *)this + 1164) = top;
        *((_DWORD *)this + 1165) = right;
        *((_DWORD *)this + 1166) = bottom;
      }
      v23 = a2->right - a2->left;
      v24 = a2->bottom - a2->top;
      if ( *((_DWORD *)this + 1178) - *((_DWORD *)this + 1176) > v24
        && *((_DWORD *)this + 1177) - *((_DWORD *)this + 1175) > v23 )
      {
        *(struct tagRECT *)((char *)this + 4700) = *a2;
      }
      if ( *((_DWORD *)this + 1174) - *((_DWORD *)this + 1172) < v24
        && *((_DWORD *)this + 1173) - *((_DWORD *)this + 1171) < v23 )
      {
        *(struct tagRECT *)((char *)this + 4684) = *a2;
      }
    }
    return;
  }
  LastError = GetLastError();
  v13 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v13 = LastError < 0;
  }
  if ( v13 )
  {
    v10 = "GetWindowInfo failed or returned empty rect in UpdateFullscreenPresentInfo";
    v11 = LastError;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x180045b98  mov     [rsp-28h+arg_10], rbx
0x180045b9d  mov     [rsp-28h+arg_18], rsi
0x180045ba2  push    rbp
0x180045ba3  push    rdi
0x180045ba4  push    r12
0x180045ba6  push    r14
0x180045ba8  push    r15
0x180045baa  mov     rbp, rsp
0x180045bad  sub     rsp, 80h
0x180045bb4  mov     rax, cs:__security_cookie
0x180045bbb  xor     rax, rsp
0x180045bbe  mov     [rbp+var_10], rax
0x180045bc2  xorps   xmm0, xmm0
0x180045bc5  mov     rbx, rcx
0x180045bc8  mov     ecx, [rcx+808h]; this
0x180045bce  mov     r15d, r8d
0x180045bd1  movups  xmmword ptr [rbp+pwi.cbSize], xmm0
0x180045bd5  mov     rdi, rdx
0x180045bd8  mov     [rbp+pwi.cbSize], 3Ch ; '<'
0x180045bdf  lea     rsi, [rbx+80Ch]
0x180045be6  movups  xmmword ptr [rbp+pwi.rcClient.bottom], xmm0
0x180045bea  movups  xmmword ptr [rbp+pwi.rcWindow.bottom], xmm0
0x180045bee  movups  xmmword ptr [rbp+pwi.dwWindowStatus], xmm0
0x180045bf2  cmp     [rbx+178h], ecx
0x180045bf8  jnz     loc_180045CEA
0x180045bfe  mov     eax, [rsi]
0x180045c00  cmp     [rbx+17Ch], eax
0x180045c06  jnz     loc_180045CEA
0x180045c0c  mov     r14b, 1
0x180045c0f  mov     eax, [rdx+8]
0x180045c12  sub     eax, [rdx]
0x180045c14  cmp     ecx, eax
0x180045c16  jnz     loc_180045CD7
0x180045c1c  mov     eax, [rdx+0Ch]
0x180045c1f  sub     eax, [rdx+4]
0x180045c22  cmp     [rsi], eax
0x180045c24  jnz     loc_180045CD7
0x180045c2a  mov     rcx, rdi; lprc
0x180045c2d  call    cs:__imp_IsRectEmpty
0x180045c33  test    eax, eax
0x180045c35  jnz     loc_180045CD7
0x180045c3b  test    r15d, r15d
0x180045c3e  jz      loc_180045CD7
0x180045c44  mov     rcx, [rbx+150h]; hwnd
0x180045c4b  lea     rdx, [rbp+pwi]; pwi
0x180045c4f  call    cs:__imp_GetWindowInfo
0x180045c55  test    eax, eax
0x180045c57  jz      loc_180045CF2
0x180045c5d  lea     rcx, [rbp+pwi.rcWindow]; lprc
0x180045c61  call    cs:__imp_IsRectEmpty
0x180045c67  test    eax, eax
0x180045c69  jnz     loc_180045CF2
0x180045c6f  lea     rcx, [rbp+pwi.rcClient]; lprc
0x180045c73  call    cs:__imp_IsRectEmpty
0x180045c79  test    eax, eax
0x180045c7b  jnz     short loc_180045CF2
0x180045c7d  cmp     r15d, 1
0x180045c81  jnz     loc_180045ED4
0x180045c87  lea     rdx, [rbp+pwi.rcClient]; lprc2
0x180045c8b  lea     rcx, [rbp+pwi.rcWindow]; lprc1
0x180045c8f  call    cs:__imp_EqualRect
0x180045c95  test    eax, eax
0x180045c97  jz      short loc_180045D15
0x180045c99  mov     rdx, rdi; lprc2
0x180045c9c  lea     rcx, [rbp+pwi.rcWindow]; lprc1
0x180045ca0  call    cs:__imp_EqualRect
0x180045ca6  test    eax, eax
0x180045ca8  jz      short loc_180045D15
0x180045caa  test    r14b, r14b
0x180045cad  jz      short loc_180045D15
0x180045caf  mov     rcx, [rbp+var_10]
0x180045cb3  xor     rcx, rsp; StackCookie
0x180045cb6  call    __security_check_cookie
0x180045cbb  lea     r11, [rsp+80h+var_s0]
0x180045cc3  mov     rbx, [r11+40h]
0x180045cc7  mov     rsi, [r11+48h]
0x180045ccb  mov     rsp, r11
0x180045cce  pop     r15
0x180045cd0  pop     r14
0x180045cd2  pop     r12
0x180045cd4  pop     rdi
0x180045cd5  pop     rbp
0x180045cd6  retn
0x180045cd7  lea     r8, aInvalidDisplay; "Invalid DisplayModeDesc and DisplayRect"...
0x180045cde  mov     edx, 8000FFFFh; unsigned int
0x180045ce3  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180045ce8  jmp     short loc_180045CAF
0x180045cea  xor     r14b, r14b
0x180045ced  jmp     loc_180045C0F
0x180045cf2  call    cs:__imp_GetLastError
0x180045cf8  test    eax, eax
0x180045cfa  jg      short loc_180045D09
0x180045cfc  jns     short loc_180045CAF
0x180045cfe  lea     r8, aGetwindowinfoF; "GetWindowInfo failed or returned empty "...
0x180045d05  mov     edx, eax
0x180045d07  jmp     short loc_180045CE3
0x180045d09  movzx   eax, ax
0x180045d0c  or      eax, 80070000h
0x180045d11  test    eax, eax
0x180045d13  jmp     short loc_180045CFC
0x180045d15  mov     r12d, [rbp+pwi.rcWindow.right]
0x180045d19  lea     rdx, [rbp+pwi.rcClient]; lprc2
0x180045d1d  mov     r15d, [rbp+pwi.rcWindow.bottom]
0x180045d21  lea     rcx, [rbp+pwi.rcWindow]; lprc1
0x180045d25  sub     r12d, [rbp+pwi.rcWindow.left]
0x180045d29  sub     r15d, [rbp+pwi.rcWindow.top]
0x180045d2d  inc     dword ptr [rbx+11F4h]
0x180045d33  call    cs:__imp_EqualRect
0x180045d39  test    eax, eax
0x180045d3b  jz      loc_180045EDF
0x180045d41  mov     rdx, rdi; lprc2
0x180045d44  lea     rcx, [rbp+pwi.rcWindow]; lprc1
0x180045d48  call    cs:__imp_EqualRect
0x180045d4e  test    eax, eax
0x180045d50  jz      loc_180045EEA
0x180045d56  cmp     r12d, [rbx+178h]
0x180045d5d  jnz     loc_180045EBE
0x180045d63  cmp     r15d, [rbx+17Ch]
0x180045d6a  jnz     loc_180045EBE
0x180045d70  test    r14b, r14b
0x180045d73  jnz     short loc_180045D7B
0x180045d75  inc     dword ptr [rbx+1204h]
0x180045d7b  mov     eax, [rdi+4]
0x180045d7e  cmp     [rbp+pwi.rcWindow.top], eax
0x180045d81  jnz     loc_180045EF5
0x180045d87  mov     eax, [rdi]
0x180045d89  cmp     [rbp+pwi.rcWindow.left], eax
0x180045d8c  jnz     loc_180045EF5
0x180045d92  xorps   xmm0, xmm0
0x180045d95  lea     rdx, [rbp+pwi.rcWindow]; lprcSrc1
0x180045d99  mov     r8, rdi; lprcSrc2
0x180045d9c  lea     rcx, [rbp+rcDst]; lprcDst
0x180045da0  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x180045da4  call    cs:__imp_IntersectRect
0x180045daa  test    eax, eax
0x180045dac  jz      short loc_180045DC2
0x180045dae  lea     rcx, [rbp+rcDst]; lprc
0x180045db2  call    cs:__imp_IsRectEmpty
0x180045db8  test    eax, eax
0x180045dba  jnz     short loc_180045DC2
0x180045dbc  inc     dword ptr [rbx+120Ch]
0x180045dc2  cmp     r15d, [rsi]
0x180045dc5  jbe     short loc_180045DCD
0x180045dc7  inc     dword ptr [rbx+1210h]
0x180045dcd  mov     eax, [rbx+808h]
0x180045dd3  cmp     r12d, eax
0x180045dd6  jbe     short loc_180045DDE
0x180045dd8  inc     dword ptr [rbx+1214h]
0x180045dde  cmp     eax, [rbx+178h]
0x180045de4  jnz     loc_180045EC9
0x180045dea  mov     eax, [rbx+17Ch]
0x180045df0  cmp     [rsi], eax
0x180045df2  jnz     loc_180045EC9
0x180045df8  mov     eax, [rbx+810h]
0x180045dfe  mov     edx, [rbx+184h]
0x180045e04  mov     ecx, [rbx+814h]
0x180045e0a  imul    rdx, rax
0x180045e0e  mov     eax, [rbx+180h]
0x180045e14  imul    rcx, rax
0x180045e18  cmp     rdx, rcx
0x180045e1b  jz      short loc_180045E23
0x180045e1d  inc     dword ptr [rbx+121Ch]
0x180045e23  mov     r8d, [rbp+pwi.rcWindow.right]
0x180045e27  mov     ecx, r8d
0x180045e2a  mov     r10d, [rbp+pwi.rcWindow.bottom]
0x180045e2e  mov     edx, r10d
0x180045e31  mov     eax, [rbx+1248h]
0x180045e37  mov     r9d, [rbp+pwi.rcWindow.left]
0x180045e3b  sub     ecx, r9d
0x180045e3e  mov     r11d, [rbp+pwi.rcWindow.top]
0x180045e42  sub     edx, r11d
0x180045e45  sub     eax, [rbx+1240h]
0x180045e4b  cmp     eax, edx
0x180045e4d  jg      loc_180045F00
0x180045e53  mov     eax, [rbx+1238h]
0x180045e59  sub     eax, [rbx+1230h]
0x180045e5f  cmp     eax, edx
0x180045e61  jl      loc_180045F35
0x180045e67  mov     ecx, [rdi+8]
0x180045e6a  mov     edx, [rdi+0Ch]
0x180045e6d  mov     eax, [rbx+1268h]
0x180045e73  sub     ecx, [rdi]
0x180045e75  sub     edx, [rdi+4]
0x180045e78  sub     eax, [rbx+1260h]
0x180045e7e  cmp     eax, edx
0x180045e80  jg      loc_180045F6A
0x180045e86  mov     eax, [rbx+1258h]
0x180045e8c  sub     eax, [rbx+1250h]
0x180045e92  cmp     eax, edx
0x180045e94  jge     loc_180045CAF
0x180045e9a  mov     eax, [rbx+1254h]
0x180045ea0  sub     eax, [rbx+124Ch]
0x180045ea6  cmp     eax, ecx
0x180045ea8  jge     loc_180045CAF
0x180045eae  movups  xmm0, xmmword ptr [rdi]
0x180045eb1  movdqu  xmmword ptr [rbx+124Ch], xmm0
0x180045eb9  jmp     loc_180045CAF
0x180045ebe  inc     dword ptr [rbx+1200h]
0x180045ec4  jmp     loc_180045D70
0x180045ec9  inc     dword ptr [rbx+1218h]
0x180045ecf  jmp     loc_180045DF8
0x180045ed4  inc     dword ptr [rbx+11F0h]
0x180045eda  jmp     loc_180045C87
0x180045edf  inc     dword ptr [rbx+11F8h]
0x180045ee5  jmp     loc_180045D41
0x180045eea  inc     dword ptr [rbx+11FCh]
0x180045ef0  jmp     loc_180045D56
0x180045ef5  inc     dword ptr [rbx+1208h]
0x180045efb  jmp     loc_180045D92
0x180045f00  mov     eax, [rbx+1244h]
0x180045f06  sub     eax, [rbx+123Ch]
0x180045f0c  cmp     eax, ecx
0x180045f0e  jle     loc_180045E53
0x180045f14  mov     [rbx+123Ch], r9d
0x180045f1b  mov     [rbx+1240h], r11d
0x180045f22  mov     [rbx+1244h], r8d
0x180045f29  mov     [rbx+1248h], r10d
0x180045f30  jmp     loc_180045E53
0x180045f35  mov     eax, [rbx+1234h]
0x180045f3b  sub     eax, [rbx+122Ch]
0x180045f41  cmp     eax, ecx
0x180045f43  jge     loc_180045E67
0x180045f49  mov     [rbx+122Ch], r9d
0x180045f50  mov     [rbx+1230h], r11d
0x180045f57  mov     [rbx+1234h], r8d
0x180045f5e  mov     [rbx+1238h], r10d
0x180045f65  jmp     loc_180045E67
0x180045f6a  mov     eax, [rbx+1264h]
0x180045f70  sub     eax, [rbx+125Ch]
0x180045f76  cmp     eax, ecx
0x180045f78  jle     loc_180045E86
0x180045f7e  movups  xmm0, xmmword ptr [rdi]
0x180045f81  movdqu  xmmword ptr [rbx+125Ch], xmm0
0x180045f89  jmp     loc_180045E86
```
