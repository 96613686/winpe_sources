# REExtendedRegisterClass(void)

- ea: `0x180075750`
- end: `0x180075859`
- name: `?REExtendedRegisterClass@@YAHXZ`
- size: `265`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180026b9c`
- `0x180075750`

## string_xrefs

- `0x180075808`: `REComboBox20W`

## pseudocode

```c
__int64 REExtendedRegisterClass(void)
{
  __int64 result; // rax
  __m128i si128; // xmm6
  bool v2; // zf
  WNDCLASSW WndClass; // [rsp+20h] [rbp-60h] BYREF

  result = CW32System::_fRegisteredXBox;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(&WndClass.style + 1) = 0;
  if ( (CW32System::_fRegisteredXBox & 1) == 0 )
  {
    WndClass.style = 16520;
    WndClass.lpfnWndProc = (WNDPROC)RichListBoxWndProc;
    WndClass.hInstance = hinstRE;
    WndClass.cbClsExtra = 0;
    WndClass.lpszClassName = aRelistbox20w_1;
    WndClass.cbWndExtra = 8;
    *(_OWORD *)&WndClass.hIcon = 0;
    *(__m128i *)&WndClass.hbrBackground = si128;
    v2 = CW32System::RegisterREClass(&WndClass, 0, 0) == 0;
    result = CW32System::_fRegisteredXBox;
    if ( !v2 )
    {
      result = CW32System::_fRegisteredXBox | 1;
      CW32System::_fRegisteredXBox |= 1u;
    }
  }
  if ( (result & 2) == 0 )
  {
    WndClass.style = 16523;
    WndClass.lpfnWndProc = (WNDPROC)RichComboBoxWndProc;
    WndClass.hInstance = hinstRE;
    WndClass.cbClsExtra = 0;
    WndClass.lpszClassName = aRecombobox20w;
    WndClass.cbWndExtra = 8;
    *(_OWORD *)&WndClass.hIcon = 0;
    *(__m128i *)&WndClass.hbrBackground = si128;
    v2 = CW32System::RegisterREClass(&WndClass, 0, 0) == 0;
    result = CW32System::_fRegisteredXBox;
    if ( !v2 )
    {
      result = CW32System::_fRegisteredXBox | 2;
      CW32System::_fRegisteredXBox |= 2u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180075750  mov     [rsp-8+arg_0], rbx
0x180075755  push    rbp
0x180075756  mov     rbp, rsp
0x180075759  sub     rsp, 80h
0x180075760  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x180075766  xor     ebx, ebx
0x180075768  movaps  [rsp+80h+var_10], xmm6
0x18007576d  movdqa  xmm6, cs:__xmm@00000000000000000000000000000006
0x180075775  mov     dword ptr [rbp+WndClass+4], ebx
0x180075778  test    al, 1
0x18007577a  jnz     short loc_1800757DD
0x18007577c  lea     rax, ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180075783  mov     [rbp+WndClass.style], 4088h
0x18007578a  mov     [rbp+WndClass.lpfnWndProc], rax
0x18007578e  lea     rcx, [rbp+WndClass]; lpWndClass
0x180075792  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x180075799  xorps   xmm0, xmm0
0x18007579c  mov     [rbp+WndClass.hInstance], rax
0x1800757a0  xor     r8d, r8d; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x1800757a3  lea     rax, aRelistbox20w_1; "REListBox20W"
0x1800757aa  mov     [rbp+WndClass.cbClsExtra], ebx
0x1800757ad  xor     edx, edx; lpString
0x1800757af  mov     [rbp+WndClass.lpszClassName], rax
0x1800757b3  mov     [rbp+WndClass.cbWndExtra], 8
0x1800757ba  movdqa  xmmword ptr [rbp+WndClass.hIcon], xmm0
0x1800757bf  movdqa  xmmword ptr [rbp+WndClass.hbrBackground], xmm6
0x1800757c4  call    ?RegisterREClass@CW32System@@SAGPEBUtagWNDCLASSW@@PEBDP6A_JPEAUHWND__@@I_K_J@Z@Z; CW32System::RegisterREClass(tagWNDCLASSW const *,char const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x1800757c9  test    ax, ax
0x1800757cc  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x1800757d2  jz      short loc_1800757DD
0x1800757d4  or      eax, 1
0x1800757d7  mov     cs:?_fRegisteredXBox@CW32System@@2IA, eax; uint CW32System::_fRegisteredXBox
0x1800757dd  test    al, 2
0x1800757df  jnz     short loc_180075842
0x1800757e1  lea     rax, ?RichComboBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichComboBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800757e8  mov     [rbp+WndClass.style], 408Bh
0x1800757ef  mov     [rbp+WndClass.lpfnWndProc], rax
0x1800757f3  lea     rcx, [rbp+WndClass]; lpWndClass
0x1800757f7  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x1800757fe  xorps   xmm0, xmm0
0x180075801  mov     [rbp+WndClass.hInstance], rax
0x180075805  xor     r8d, r8d; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x180075808  lea     rax, aRecombobox20w; "REComboBox20W"
0x18007580f  mov     [rbp+WndClass.cbClsExtra], ebx
0x180075812  xor     edx, edx; lpString
0x180075814  mov     [rbp+WndClass.lpszClassName], rax
0x180075818  mov     [rbp+WndClass.cbWndExtra], 8
0x18007581f  movdqa  xmmword ptr [rbp+WndClass.hIcon], xmm0
0x180075824  movdqa  xmmword ptr [rbp+WndClass.hbrBackground], xmm6
0x180075829  call    ?RegisterREClass@CW32System@@SAGPEBUtagWNDCLASSW@@PEBDP6A_JPEAUHWND__@@I_K_J@Z@Z; CW32System::RegisterREClass(tagWNDCLASSW const *,char const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x18007582e  test    ax, ax
0x180075831  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x180075837  jz      short loc_180075842
0x180075839  or      eax, 2
0x18007583c  mov     cs:?_fRegisteredXBox@CW32System@@2IA, eax; uint CW32System::_fRegisteredXBox
0x180075842  mov     rbx, [rsp+80h+arg_0]
0x18007584a  movaps  xmm6, [rsp+80h+var_10]
0x18007584f  add     rsp, 80h
0x180075856  pop     rbp
0x180075857  retn
```
