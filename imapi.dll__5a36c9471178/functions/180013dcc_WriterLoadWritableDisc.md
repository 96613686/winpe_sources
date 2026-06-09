# WriterLoadWritableDisc

- ea: `0x180013dcc`
- end: `0x180013f3b`
- name: `WriterLoadWritableDisc`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d830`

## callees

- `0x180007bac`
- `0x180007d40`
- `0x180007d80`
- `0x180013dcc`
- `0x180014288`

## pseudocode

```c
__int64 __fastcall WriterLoadWritableDisc(__int64 a1, int a2)
{
  _QWORD *v4; // rcx
  int v5; // ebx
  unsigned int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  v8 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 53, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
    {
      WPP_SF_(v4[7], 54, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    v5 = -2147024809;
    goto LABEL_14;
  }
  v5 = WriterQueryMediaType(
         *(_QWORD *)a1,
         *(struct IDiscRecorder2Ex **)(a1 + 8),
         (enum _IMAPI_MEDIA_PHYSICAL_TYPE *)&v8,
         &v7);
  if ( v5 >= 0 )
  {
    if ( a2 == 1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      if ( (v7 & 1) == 0 )
      {
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
        {
          WPP_SF_(v4[7], 57, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        v5 = -2147220976;
      }
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
LABEL_13:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_14:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
    WPP_SF_qD(v4[7], 58, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013dcc  mov     rax, rsp
0x180013dcf  mov     [rax+10h], rbx
0x180013dd3  mov     [rax+20h], rsi
0x180013dd7  push    rdi
0x180013dd8  push    r14
0x180013dda  push    r15
0x180013ddc  sub     rsp, 30h
0x180013de0  mov     esi, edx
0x180013de2  mov     dword ptr [rax+8], 0
0x180013de9  mov     rdi, rcx
0x180013dec  mov     dword ptr [rax+18h], 0
0x180013df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dfa  lea     r14, WPP_GLOBAL_Control
0x180013e01  lea     r15, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013e08  cmp     rcx, r14
0x180013e0b  jz      short loc_180013E2E
0x180013e0d  test    byte ptr [rcx+44h], 1
0x180013e11  jz      short loc_180013E2E
0x180013e13  mov     rcx, [rcx+38h]
0x180013e17  mov     edx, 35h ; '5'
0x180013e1c  mov     r9, rdi
0x180013e1f  mov     r8, r15
0x180013e22  call    WPP_SF_q
0x180013e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e2e  test    rdi, rdi
0x180013e31  jnz     short loc_180013E5B
0x180013e33  cmp     rcx, r14
0x180013e36  jz      short loc_180013E54
0x180013e38  test    byte ptr [rcx+44h], 1
0x180013e3c  jz      short loc_180013E54
0x180013e3e  mov     rcx, [rcx+38h]
0x180013e42  lea     edx, [rdi+36h]
0x180013e45  mov     r8, r15
0x180013e48  call    WPP_SF_
0x180013e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e54  mov     ebx, 80070057h
0x180013e59  jmp     short loc_180013EA1
0x180013e5b  mov     rdx, [rdi+8]
0x180013e5f  lea     r9, [rsp+48h+arg_0]
0x180013e64  mov     rcx, [rdi]
0x180013e67  lea     r8, [rsp+48h+arg_10]
0x180013e6c  call    WriterQueryMediaType
0x180013e71  mov     ebx, eax
0x180013e73  test    eax, eax
0x180013e75  jns     short loc_180013EDA
0x180013e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e7e  cmp     rcx, r14
0x180013e81  jz      short loc_180013EC4
0x180013e83  test    byte ptr [rcx+44h], 1
0x180013e87  jz      short loc_180013EA1
0x180013e89  mov     rcx, [rcx+38h]
0x180013e8d  mov     edx, 37h ; '7'
0x180013e92  mov     r8, r15
0x180013e95  call    WPP_SF_
0x180013e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ea1  cmp     rcx, r14
0x180013ea4  jz      short loc_180013EC4
0x180013ea6  test    byte ptr [rcx+44h], 1
0x180013eaa  jz      short loc_180013EC4
0x180013eac  mov     rcx, [rcx+38h]
0x180013eb0  mov     edx, 3Ah ; ':'
0x180013eb5  mov     r9, rdi
0x180013eb8  mov     [rsp+48h+var_28], ebx
0x180013ebc  mov     r8, r15
0x180013ebf  call    WPP_SF_qD
0x180013ec4  mov     rsi, [rsp+48h+arg_18]
0x180013ec9  mov     eax, ebx
0x180013ecb  mov     rbx, [rsp+48h+arg_8]
0x180013ed0  add     rsp, 30h
0x180013ed4  pop     r15
0x180013ed6  pop     r14
0x180013ed8  pop     rdi
0x180013ed9  retn
0x180013eda  cmp     esi, 1
0x180013edd  jnz     short loc_180013E9A
0x180013edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee6  cmp     rcx, r14
0x180013ee9  jz      short loc_180013F07
0x180013eeb  test    [rcx+44h], sil
0x180013eef  jz      short loc_180013F07
0x180013ef1  mov     rcx, [rcx+38h]
0x180013ef5  lea     edx, [rsi+37h]
0x180013ef8  mov     r8, r15
0x180013efb  call    WPP_SF_
0x180013f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f07  test    byte ptr [rsp+48h+arg_0], 1
0x180013f0c  jnz     short loc_180013EA1
0x180013f0e  cmp     rcx, r14
0x180013f11  jz      short loc_180013F31
0x180013f13  test    byte ptr [rcx+44h], 1
0x180013f17  jz      short loc_180013F31
0x180013f19  mov     rcx, [rcx+38h]
0x180013f1d  mov     edx, 39h ; '9'
0x180013f22  mov     r8, r15
0x180013f25  call    WPP_SF_
0x180013f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f31  mov     ebx, 80040210h
0x180013f36  jmp     loc_180013EA1
```
