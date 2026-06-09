# LipsApiIkeFilterUpdate

- ea: `0x180044928`
- end: `0x180044a34`
- name: `LipsApiIkeFilterUpdate`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800240cc`
- `0x180024750`

## callees

- `0x18000e510`
- `0x18000f6ac`
- `0x180044928`
- `0x180045c1c`

## string_xrefs

- `0x18004495a`: `LipsApiIkeFilterUpdate`
- `0x1800449a1`: `LipsApiIkeFilterUpdate`

## pseudocode

```c
__int64 __fastcall LipsApiIkeFilterUpdate(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids,
      "LipsApiIkeFilterUpdate");
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && (*(_DWORD *)(a1 + 36) & 0x100) != 0 || a2 && (*(_DWORD *)(a2 + 36) & 0x100) != 0 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_s(v4[2], 30, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, "LipsApiIkeFilterUpdate");
    return 0;
  }
  else
  {
    v6 = LipsStateIkeFilterUpdate(a1, a2);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v6);
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
          WPP_SF_d(v8[2], 32, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids, v7);
      }
    }
    return v7;
  }
}

```

## disassembly

```asm
0x180044928  mov     [rsp+arg_0], rbx
0x18004492d  mov     [rsp+arg_8], rsi
0x180044932  push    rdi
0x180044933  sub     rsp, 20h
0x180044937  mov     rbx, rdx
0x18004493a  mov     rdi, rcx
0x18004493d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044944  lea     rsi, WPP_GLOBAL_Control
0x18004494b  cmp     rcx, rsi
0x18004494e  jz      short loc_180044979
0x180044950  test    byte ptr [rcx+1Ch], 4
0x180044954  jz      short loc_180044979
0x180044956  mov     rcx, [rcx+10h]
0x18004495a  lea     r9, aLipsapiikefilt_1; "LipsApiIkeFilterUpdate"
0x180044961  mov     edx, 1Dh
0x180044966  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x18004496d  call    WPP_SF_s
0x180044972  mov     rcx, cs:WPP_GLOBAL_Control
0x180044979  mov     eax, 100h
0x18004497e  test    rdi, rdi
0x180044981  jz      short loc_180044988
0x180044983  test    [rdi+24h], eax
0x180044986  jnz     short loc_180044992
0x180044988  test    rbx, rbx
0x18004498b  jz      short loc_1800449BD
0x18004498d  test    [rbx+24h], eax
0x180044990  jz      short loc_1800449BD
0x180044992  cmp     rcx, rsi
0x180044995  jz      short loc_1800449B9
0x180044997  test    byte ptr [rcx+1Ch], 4
0x18004499b  jz      short loc_1800449B9
0x18004499d  mov     rcx, [rcx+10h]
0x1800449a1  lea     r9, aLipsapiikefilt_1; "LipsApiIkeFilterUpdate"
0x1800449a8  mov     edx, 1Eh
0x1800449ad  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800449b4  call    WPP_SF_s
0x1800449b9  xor     eax, eax
0x1800449bb  jmp     short loc_180044A24
0x1800449bd  mov     rdx, rbx
0x1800449c0  mov     rcx, rdi
0x1800449c3  call    LipsStateIkeFilterUpdate
0x1800449c8  mov     ebx, eax
0x1800449ca  test    eax, eax
0x1800449cc  jz      short loc_180044A22
0x1800449ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449d5  cmp     rcx, rsi
0x1800449d8  jz      short loc_180044A22
0x1800449da  test    byte ptr [rcx+1Ch], 10h
0x1800449de  jz      short loc_1800449FF
0x1800449e0  mov     rcx, [rcx+10h]
0x1800449e4  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x1800449eb  mov     edx, 1Fh
0x1800449f0  mov     r9d, eax
0x1800449f3  call    WPP_SF_d
0x1800449f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800449ff  cmp     rcx, rsi
0x180044a02  jz      short loc_180044A22
0x180044a04  test    byte ptr [rcx+1Ch], 10h
0x180044a08  jz      short loc_180044A22
0x180044a0a  mov     rcx, [rcx+10h]
0x180044a0e  lea     r8, WPP_6c28d6ca87f73c2f8318cffb552dbdfc_Traceguids
0x180044a15  mov     edx, 20h ; ' '
0x180044a1a  mov     r9d, ebx
0x180044a1d  call    WPP_SF_d
0x180044a22  mov     eax, ebx
0x180044a24  mov     rbx, [rsp+28h+arg_0]
0x180044a29  mov     rsi, [rsp+28h+arg_8]
0x180044a2e  add     rsp, 20h
0x180044a32  pop     rdi
0x180044a33  retn
```
