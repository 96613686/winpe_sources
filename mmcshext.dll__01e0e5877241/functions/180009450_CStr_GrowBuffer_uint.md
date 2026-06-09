# CStr::GrowBuffer(uint)

- ea: `0x180009450`
- end: `0x180009576`
- name: `?GrowBuffer@CStr@@IEAAJI@Z`
- size: `294`
- prototype: `int(CStr *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180008cf8`
- `0x180009394`

## callees

- `0x180001d06`
- `0x180002c40`
- `0x180007dec`
- `0x180009450`
- `0x180009c90`
- `0x180009e74`

## pseudocode

```c
__int64 __fastcall CStr::GrowBuffer(CStr *this, unsigned int a2)
{
  CHeapFactory *v3; // rcx
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  unsigned __int16 v7; // dx
  int v8; // r9d
  int v9; // esi
  void *v10; // rax
  void *v11; // rbp
  CHeapFactory *v12; // rcx
  unsigned __int16 near **v13; // rdx

  v3 = (CHeapFactory *)*((unsigned int *)this + 4);
  if ( a2 < 0x7FFFFFFF - (int)v3 )
  {
    if ( *((_DWORD *)this + 6) )
    {
      v5 = -2147023537;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_46616a5bce583dfc538f214383f522c0_Traceguids);
    }
    else
    {
      v5 = 0;
      v9 = (_DWORD)v3 + a2;
      if ( (unsigned int)v3 + a2 <= *((_DWORD *)this + 5) )
        return v5;
      v10 = CHeapFactory::Alloc(v3, 2LL * (unsigned int)(v9 + 1), a2);
      v11 = v10;
      if ( v10 )
      {
        memcpy_0(v10, *((const void **)this + 1), 2LL * (unsigned int)(*((_DWORD *)this + 4) + 1));
        v13 = (unsigned __int16 near **)*((_QWORD *)this + 1);
        if ( v13 != &CStr::s_rgwchEmptyStringBuffer )
          CHeapFactory::Free(v12, v13);
        *((_QWORD *)this + 1) = v11;
        *((_DWORD *)this + 5) = v9;
      }
      else
      {
        v5 = -2147024882;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 22;
          v8 = v9;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 20;
      v8 = a2;
LABEL_5:
      WPP_SF_d(v6[2], v7, (__int64)WPP_46616a5bce583dfc538f214383f522c0_Traceguids, v8);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180009450  push    rbx
0x180009452  push    rbp
0x180009453  push    rsi
0x180009454  push    rdi
0x180009455  sub     rsp, 28h
0x180009459  mov     rbx, rcx
0x18000945c  mov     eax, 7FFFFFFFh
0x180009461  mov     ecx, [rcx+10h]; this
0x180009464  mov     r8d, edx; unsigned int
0x180009467  sub     eax, ecx
0x180009469  cmp     edx, eax
0x18000946b  jb      short loc_1800094B0
0x18000946d  mov     edi, 80070057h
0x180009472  mov     rcx, cs:WPP_GLOBAL_Control
0x180009479  lea     rax, WPP_GLOBAL_Control
0x180009480  cmp     rcx, rax
0x180009483  jz      loc_18000956B
0x180009489  cmp     byte ptr [rcx+19h], 2
0x18000948d  jb      loc_18000956B
0x180009493  mov     edx, 14h
0x180009498  mov     r9d, r8d
0x18000949b  mov     rcx, [rcx+10h]
0x18000949f  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x1800094a6  call    WPP_SF_d
0x1800094ab  jmp     loc_18000956B
0x1800094b0  cmp     dword ptr [rbx+18h], 0
0x1800094b4  jz      short loc_1800094F3
0x1800094b6  mov     edi, 8007054Fh
0x1800094bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094c2  lea     rax, WPP_GLOBAL_Control
0x1800094c9  cmp     rcx, rax
0x1800094cc  jz      loc_18000956B
0x1800094d2  cmp     byte ptr [rcx+19h], 1
0x1800094d6  jb      loc_18000956B
0x1800094dc  mov     rcx, [rcx+10h]
0x1800094e0  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x1800094e7  mov     edx, 15h
0x1800094ec  call    WPP_SF_
0x1800094f1  jmp     short loc_18000956B
0x1800094f3  xor     edi, edi
0x1800094f5  lea     esi, [rcx+rdx]
0x1800094f8  cmp     esi, [rbx+14h]
0x1800094fb  jbe     short loc_18000956B
0x1800094fd  lea     edx, [rsi+1]
0x180009500  add     rdx, rdx; unsigned __int64
0x180009503  call    ?Alloc@CHeapFactory@@QEAAPEAX_KK@Z; CHeapFactory::Alloc(unsigned __int64,ulong)
0x180009508  mov     rbp, rax
0x18000950b  test    rax, rax
0x18000950e  jnz     short loc_180009539
0x180009510  mov     edi, 8007000Eh
0x180009515  mov     rcx, cs:WPP_GLOBAL_Control
0x18000951c  lea     rax, WPP_GLOBAL_Control
0x180009523  cmp     rcx, rax
0x180009526  jz      short loc_18000956B
0x180009528  cmp     byte ptr [rcx+19h], 2
0x18000952c  jb      short loc_18000956B
0x18000952e  lea     edx, [rbp+16h]
0x180009531  mov     r9d, esi
0x180009534  jmp     loc_18000949B
0x180009539  mov     r8d, [rbx+10h]
0x18000953d  mov     rcx, rbp; void *
0x180009540  mov     rdx, [rbx+8]; Src
0x180009544  inc     r8d
0x180009547  add     r8, r8; Size
0x18000954a  call    memcpy_0
0x18000954f  mov     rdx, [rbx+8]; void *
0x180009553  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18000955a  cmp     rdx, rax
0x18000955d  jz      short loc_180009564
0x18000955f  call    ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
0x180009564  mov     [rbx+8], rbp
0x180009568  mov     [rbx+14h], esi
0x18000956b  mov     eax, edi
0x18000956d  add     rsp, 28h
0x180009571  pop     rdi
0x180009572  pop     rsi
0x180009573  pop     rbp
0x180009574  pop     rbx
0x180009575  retn
```
