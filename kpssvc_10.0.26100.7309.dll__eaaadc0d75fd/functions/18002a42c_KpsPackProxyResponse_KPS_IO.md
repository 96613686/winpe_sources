# KpsPackProxyResponse(_KPS_IO *)

- ea: `0x18002a42c`
- end: `0x18002a5a1`
- name: `?KpsPackProxyResponse@@YAKPEAU_KPS_IO@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180022708`

## callees

- `0x18001ae38`
- `0x180026a08`
- `0x180026d9c`
- `0x1800285a0`
- `0x1800289f8`
- `0x18002a42c`
- `0x18003012c`

## string_xrefs

- `0x18002a515`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsPackProxyResponse(struct _KPS_IO *a1)
{
  unsigned __int8 *v1; // rbx
  unsigned int v3; // eax
  unsigned int v4; // ecx
  unsigned int v5; // edi
  __int128 v7; // [rsp+30h] [rbp-30h] BYREF
  __int128 v8; // [rsp+40h] [rbp-20h]
  __int64 v9; // [rsp+50h] [rbp-10h]
  unsigned int v10; // [rsp+88h] [rbp+28h] BYREF
  unsigned __int8 *v11; // [rsp+90h] [rbp+30h] BYREF

  v1 = 0;
  v9 = 0;
  v11 = 0;
  v10 = 0;
  v7 = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
  v3 = KpsCheckKerbResponse(a1);
  v5 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v3);
  }
  else
  {
    *(_QWORD *)&v8 = *((_QWORD *)a1 + 32);
    DWORD2(v7) = *((_DWORD *)a1 + 66);
    v5 = KpsDerPack(v4, &v7, &v11, &v10);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          147,
          (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
          v5,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
          2592,
          (_QWORD)v7);
      v1 = v11;
    }
    else
    {
      *((_QWORD *)a1 + 34) = v11;
      *((_DWORD *)a1 + 70) = v10;
    }
  }
  KpsFreeMem(v1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002a42c  mov     [rsp-18h+arg_0], rbx
0x18002a431  mov     [rsp-18h+arg_18], rsi
0x18002a436  push    rbp
0x18002a437  push    rdi
0x18002a438  push    r14
0x18002a43a  mov     rbp, rsp
0x18002a43d  sub     rsp, 60h
0x18002a441  xor     eax, eax
0x18002a443  xorps   xmm0, xmm0
0x18002a446  xor     ebx, ebx
0x18002a448  mov     [rbp+var_10], rax
0x18002a44c  mov     [rbp+arg_10], rbx
0x18002a450  mov     rsi, rcx
0x18002a453  mov     [rbp+arg_8], ebx
0x18002a456  movups  [rbp+var_30], xmm0
0x18002a45a  movups  [rbp+var_20], xmm0
0x18002a45e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a465  lea     r14, WPP_GLOBAL_Control
0x18002a46c  cmp     rcx, r14
0x18002a46f  jz      short loc_18002A48F
0x18002a471  test    byte ptr [rcx+1Ch], 20h
0x18002a475  jz      short loc_18002A48F
0x18002a477  mov     rcx, [rcx+10h]
0x18002a47b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a482  mov     edx, 91h
0x18002a487  mov     r9, rsi
0x18002a48a  call    WPP_SF_q
0x18002a48f  mov     rcx, rsi; struct _KPS_IO *
0x18002a492  call    ?KpsCheckKerbResponse@@YAKPEAU_KPS_IO@@@Z; KpsCheckKerbResponse(_KPS_IO *)
0x18002a497  mov     edi, eax
0x18002a499  test    eax, eax
0x18002a49b  jz      short loc_18002A4D4
0x18002a49d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4a4  cmp     rcx, r14
0x18002a4a7  jz      loc_18002A557
0x18002a4ad  test    byte ptr [rcx+1Ch], 1
0x18002a4b1  jz      loc_18002A557
0x18002a4b7  mov     rcx, [rcx+10h]
0x18002a4bb  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a4c2  mov     edx, 92h
0x18002a4c7  mov     r9d, eax
0x18002a4ca  call    WPP_SF_D
0x18002a4cf  jmp     loc_18002A557
0x18002a4d4  mov     rax, [rsi+100h]
0x18002a4db  lea     r9, [rbp+arg_8]; unsigned int *
0x18002a4df  mov     qword ptr [rbp+var_20], rax
0x18002a4e3  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x18002a4e7  mov     eax, [rsi+108h]
0x18002a4ed  lea     rdx, [rbp+var_30]; void *
0x18002a4f1  mov     dword ptr [rbp+var_30+8], eax
0x18002a4f4  call    ?KpsDerPack@@YAKKPEAXPEAPEAEPEAK@Z; KpsDerPack(ulong,void *,uchar * *,ulong *)
0x18002a4f9  mov     edi, eax
0x18002a4fb  test    eax, eax
0x18002a4fd  jz      short loc_18002A543
0x18002a4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a506  cmp     rcx, r14
0x18002a509  jz      short loc_18002A53D
0x18002a50b  test    byte ptr [rcx+1Ch], 1
0x18002a50f  jz      short loc_18002A53D
0x18002a511  mov     rcx, [rcx+10h]
0x18002a515  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002a51c  mov     edx, 93h
0x18002a521  mov     [rsp+60h+var_38], 0A20h
0x18002a529  mov     r9d, edi
0x18002a52c  mov     [rsp+60h+var_40], rax
0x18002a531  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a538  call    WPP_SF_Dsd
0x18002a53d  mov     rbx, [rbp+arg_10]
0x18002a541  jmp     short loc_18002A557
0x18002a543  mov     rax, [rbp+arg_10]
0x18002a547  mov     [rsi+110h], rax
0x18002a54e  mov     eax, [rbp+arg_8]
0x18002a551  mov     [rsi+118h], eax
0x18002a557  mov     rcx, rbx; lpMem
0x18002a55a  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002a55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a566  cmp     rcx, r14
0x18002a569  jz      short loc_18002A589
0x18002a56b  test    byte ptr [rcx+1Ch], 20h
0x18002a56f  jz      short loc_18002A589
0x18002a571  mov     rcx, [rcx+10h]
0x18002a575  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a57c  mov     edx, 94h
0x18002a581  mov     r9d, edi
0x18002a584  call    WPP_SF_D
0x18002a589  lea     r11, [rsp+60h+var_s0]
0x18002a58e  mov     eax, edi
0x18002a590  mov     rbx, [r11+20h]
0x18002a594  mov     rsi, [r11+38h]
0x18002a598  mov     rsp, r11
0x18002a59b  pop     r14
0x18002a59d  pop     rdi
0x18002a59e  pop     rbp
0x18002a59f  retn
```
