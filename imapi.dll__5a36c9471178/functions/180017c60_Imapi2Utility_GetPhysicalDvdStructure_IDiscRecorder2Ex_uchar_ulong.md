# Imapi2Utility::GetPhysicalDvdStructure(IDiscRecorder2Ex *,uchar * *,ulong *)

- ea: `0x180017c60`
- end: `0x180017df9`
- name: `?GetPhysicalDvdStructure@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAPEAEPEAK@Z`
- size: `409`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800171d8`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180017c60`
- `0x180017ea8`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180017d10`
- `ole32!CoTaskMemFree` at `0x180017d10`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetPhysicalDvdStructure(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  _QWORD *v7; // rcx
  int v8; // ebx
  unsigned int v10; // eax
  __int64 v11; // r8
  _QWORD *v12; // rcx
  unsigned int v13; // edx
  unsigned int v14; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = 0;
  v14 = 0;
  if ( a2 )
  {
    v8 = 0;
    a2->lpVtbl = 0;
    v7 = WPP_GLOBAL_Control;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    v8 = -2147467261;
  }
  if ( a3 )
  {
    *(_DWORD *)a3 = 0;
    if ( v8 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(Imapi2Utility *, _QWORD, _QWORD, _QWORD, _DWORD, LPVOID *, unsigned int *))(*(_QWORD *)this + 48LL))(
              this,
              0,
              0,
              0,
              0,
              &pv,
              &v14);
      v8 = v10;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v10);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v8 >= 0 )
      {
        v13 = v14;
        if ( v14 >= 0x11 )
        {
          a2->lpVtbl = (struct IDiscRecorder2ExVtbl *)pv;
          *(_DWORD *)a3 = v13;
          return (unsigned int)v8;
        }
        v8 = -1062599937;
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 3u )
          WPP_SF_dDdD(v12[2], v14, v11, v14, v14);
      }
    }
  }
  else
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 3u )
      WPP_SF_(v7[2], 11, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    v8 = -2147467261;
  }
  CoTaskMemFree(pv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017c60  mov     rax, rsp
0x180017c63  mov     [rax+8], rbx
0x180017c67  mov     [rax+20h], rsi
0x180017c6b  push    rdi
0x180017c6c  push    r13
0x180017c6e  push    r14
0x180017c70  sub     rsp, 40h
0x180017c74  mov     qword ptr [rax+18h], 0
0x180017c7c  mov     rdi, r8
0x180017c7f  mov     dword ptr [rax+10h], 0
0x180017c86  mov     rsi, rdx
0x180017c89  lea     r13, WPP_GLOBAL_Control
0x180017c90  mov     r14, rcx
0x180017c93  test    rdx, rdx
0x180017c96  jnz     short loc_180017CD1
0x180017c98  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c9f  cmp     rcx, r13
0x180017ca2  jz      short loc_180017CCA
0x180017ca4  test    byte ptr [rcx+1Ch], 4
0x180017ca8  jz      short loc_180017CCA
0x180017caa  cmp     byte ptr [rcx+19h], 3
0x180017cae  jb      short loc_180017CCA
0x180017cb0  mov     rcx, [rcx+10h]
0x180017cb4  lea     edx, [rsi+0Ah]
0x180017cb7  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017cbe  call    WPP_SF_
0x180017cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cca  mov     ebx, 80004003h
0x180017ccf  jmp     short loc_180017CDD
0x180017cd1  xor     ebx, ebx
0x180017cd3  mov     [rdx], rbx
0x180017cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cdd  test    rdi, rdi
0x180017ce0  jnz     short loc_180017D2C
0x180017ce2  cmp     rcx, r13
0x180017ce5  jz      short loc_180017D06
0x180017ce7  test    byte ptr [rcx+1Ch], 4
0x180017ceb  jz      short loc_180017D06
0x180017ced  cmp     byte ptr [rcx+19h], 3
0x180017cf1  jb      short loc_180017D06
0x180017cf3  mov     rcx, [rcx+10h]
0x180017cf7  lea     edx, [rdi+0Bh]
0x180017cfa  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017d01  call    WPP_SF_
0x180017d06  mov     ebx, 80004003h
0x180017d0b  mov     rcx, [rsp+58h+pv]; pv
0x180017d10  call    cs:__imp_CoTaskMemFree
0x180017d16  mov     rsi, [rsp+58h+arg_18]
0x180017d1b  mov     eax, ebx
0x180017d1d  mov     rbx, [rsp+58h+arg_0]
0x180017d22  add     rsp, 40h
0x180017d26  pop     r14
0x180017d28  pop     r13
0x180017d2a  pop     rdi
0x180017d2b  retn
0x180017d2c  mov     dword ptr [rdi], 0
0x180017d32  test    ebx, ebx
0x180017d34  js      short loc_180017D0B
0x180017d36  mov     rax, [r14]
0x180017d39  lea     rcx, [rsp+58h+arg_8]
0x180017d3e  mov     [rsp+58h+var_28], rcx
0x180017d43  xor     r9d, r9d
0x180017d46  lea     rcx, [rsp+58h+pv]
0x180017d4b  xor     r8d, r8d
0x180017d4e  mov     [rsp+58h+var_30], rcx
0x180017d53  xor     edx, edx
0x180017d55  mov     rax, [rax+30h]
0x180017d59  mov     rcx, r14
0x180017d5c  mov     [rsp+58h+var_38], 0
0x180017d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d69  mov     ebx, eax
0x180017d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d72  cmp     rcx, r13
0x180017d75  jz      short loc_180017DA2
0x180017d77  test    byte ptr [rcx+1Ch], 4
0x180017d7b  jz      short loc_180017DA2
0x180017d7d  cmp     byte ptr [rcx+19h], 3
0x180017d81  jb      short loc_180017DA2
0x180017d83  mov     rcx, [rcx+10h]
0x180017d87  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017d8e  mov     edx, 0Ch
0x180017d93  mov     r9d, eax
0x180017d96  call    WPP_SF_d
0x180017d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017da2  test    ebx, ebx
0x180017da4  js      loc_180017D0B
0x180017daa  mov     edx, [rsp+58h+arg_8]
0x180017dae  cmp     edx, 11h
0x180017db1  jnb     short loc_180017DEA
0x180017db3  mov     ebx, 0C0AA02FFh
0x180017db8  cmp     rcx, r13
0x180017dbb  jz      loc_180017D0B
0x180017dc1  test    byte ptr [rcx+1Ch], 4
0x180017dc5  jz      loc_180017D0B
0x180017dcb  cmp     byte ptr [rcx+19h], 3
0x180017dcf  jb      loc_180017D0B
0x180017dd5  mov     rcx, [rcx+10h]
0x180017dd9  mov     r9d, edx
0x180017ddc  mov     [rsp+58h+var_38], edx
0x180017de0  call    WPP_SF_dDdD
0x180017de5  jmp     loc_180017D0B
0x180017dea  mov     rax, [rsp+58h+pv]
0x180017def  mov     [rsi], rax
0x180017df2  mov     [rdi], edx
0x180017df4  jmp     loc_180017D16
```
