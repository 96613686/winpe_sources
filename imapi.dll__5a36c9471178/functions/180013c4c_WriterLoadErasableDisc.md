# WriterLoadErasableDisc

- ea: `0x180013c4c`
- end: `0x180013dc4`
- name: `WriterLoadErasableDisc`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ee40`

## callees

- `0x180007bac`
- `0x180007d40`
- `0x180007d80`
- `0x180013c4c`
- `0x180014288`

## pseudocode

```c
__int64 __fastcall WriterLoadErasableDisc(__int64 a1)
{
  _QWORD *v2; // rcx
  int v3; // ebx
  unsigned int v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 1) != 0 )
    {
      WPP_SF_(v2[7], 48, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v3 = -2147024809;
    goto LABEL_14;
  }
  v3 = WriterQueryMediaType(
         *(_QWORD *)a1,
         *(struct IDiscRecorder2Ex **)(a1 + 8),
         (enum _IMAPI_MEDIA_PHYSICAL_TYPE *)&v6,
         &v5);
  if ( v3 >= 0 )
  {
    if ( !v5 && !v6 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), v5 + 50, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      v3 = -2147220977;
      goto LABEL_14;
    }
    if ( (v5 & 2) == 0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      v3 = -2147220976;
      goto LABEL_14;
    }
    goto LABEL_13;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
LABEL_13:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_14:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 1) != 0 )
    WPP_SF_qD(v2[7], 52, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013c4c  mov     [rsp+arg_10], rbx
0x180013c51  push    rdi
0x180013c52  push    r14
0x180013c54  push    r15
0x180013c56  sub     rsp, 30h
0x180013c5a  mov     rdi, rcx
0x180013c5d  mov     [rsp+48h+arg_0], 0
0x180013c65  mov     [rsp+48h+arg_8], 0
0x180013c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c74  lea     r14, WPP_GLOBAL_Control
0x180013c7b  lea     r15, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013c82  cmp     rcx, r14
0x180013c85  jz      short loc_180013CA8
0x180013c87  test    byte ptr [rcx+44h], 1
0x180013c8b  jz      short loc_180013CA8
0x180013c8d  mov     rcx, [rcx+38h]
0x180013c91  mov     edx, 2Fh ; '/'
0x180013c96  mov     r9, rdi
0x180013c99  mov     r8, r15
0x180013c9c  call    WPP_SF_q
0x180013ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ca8  test    rdi, rdi
0x180013cab  jnz     short loc_180013CD5
0x180013cad  cmp     rcx, r14
0x180013cb0  jz      short loc_180013CCE
0x180013cb2  test    byte ptr [rcx+44h], 1
0x180013cb6  jz      short loc_180013CCE
0x180013cb8  mov     rcx, [rcx+38h]
0x180013cbc  lea     edx, [rdi+30h]
0x180013cbf  mov     r8, r15
0x180013cc2  call    WPP_SF_
0x180013cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cce  mov     ebx, 80070057h
0x180013cd3  jmp     short loc_180013D1B
0x180013cd5  mov     rdx, [rdi+8]
0x180013cd9  lea     r9, [rsp+48h+arg_0]
0x180013cde  mov     rcx, [rdi]
0x180013ce1  lea     r8, [rsp+48h+arg_8]
0x180013ce6  call    WriterQueryMediaType
0x180013ceb  mov     ebx, eax
0x180013ced  test    eax, eax
0x180013cef  jns     short loc_180013D4F
0x180013cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cf8  cmp     rcx, r14
0x180013cfb  jz      short loc_180013D3E
0x180013cfd  test    byte ptr [rcx+44h], 1
0x180013d01  jz      short loc_180013D1B
0x180013d03  mov     rcx, [rcx+38h]
0x180013d07  mov     edx, 31h ; '1'
0x180013d0c  mov     r8, r15
0x180013d0f  call    WPP_SF_
0x180013d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d1b  cmp     rcx, r14
0x180013d1e  jz      short loc_180013D3E
0x180013d20  test    byte ptr [rcx+44h], 1
0x180013d24  jz      short loc_180013D3E
0x180013d26  mov     rcx, [rcx+38h]
0x180013d2a  mov     edx, 34h ; '4'
0x180013d2f  mov     r9, rdi
0x180013d32  mov     [rsp+48h+var_28], ebx
0x180013d36  mov     r8, r15
0x180013d39  call    WPP_SF_qD
0x180013d3e  mov     eax, ebx
0x180013d40  mov     rbx, [rsp+48h+arg_10]
0x180013d45  add     rsp, 30h
0x180013d49  pop     r15
0x180013d4b  pop     r14
0x180013d4d  pop     rdi
0x180013d4e  retn
0x180013d4f  mov     eax, [rsp+48h+arg_0]
0x180013d53  test    eax, eax
0x180013d55  jnz     short loc_180013D8C
0x180013d57  cmp     [rsp+48h+arg_8], eax
0x180013d5b  jnz     short loc_180013D8C
0x180013d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d64  cmp     rcx, r14
0x180013d67  jz      short loc_180013D85
0x180013d69  test    byte ptr [rcx+44h], 1
0x180013d6d  jz      short loc_180013D85
0x180013d6f  mov     rcx, [rcx+38h]
0x180013d73  lea     edx, [rax+32h]
0x180013d76  mov     r8, r15
0x180013d79  call    WPP_SF_
0x180013d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d85  mov     ebx, 8004020Fh
0x180013d8a  jmp     short loc_180013D1B
0x180013d8c  test    al, 2
0x180013d8e  jnz     short loc_180013D14
0x180013d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d97  cmp     rcx, r14
0x180013d9a  jz      short loc_180013DBA
0x180013d9c  test    byte ptr [rcx+44h], 1
0x180013da0  jz      short loc_180013DBA
0x180013da2  mov     rcx, [rcx+38h]
0x180013da6  mov     edx, 33h ; '3'
0x180013dab  mov     r8, r15
0x180013dae  call    WPP_SF_
0x180013db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dba  mov     ebx, 80040210h
0x180013dbf  jmp     loc_180013D1B
```
