# Dock::UpdateProperties(bool)

- ea: `0x180012ddc`
- end: `0x18001310c`
- name: `?UpdateProperties@Dock@@AEAAX_N@Z`
- size: `816`
- prototype: `void __fastcall(Dock *this, char)`
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180011470`
- `0x180011acc`
- `0x180012330`
- `0x180012788`
- `0x180012b34`
- `0x180012ba0`

## callees

- `0x18000c308`
- `0x18000c348`
- `0x18000cb40`
- `0x18000de64`
- `0x18000e2ac`
- `0x180012ddc`
- `0x18001ca3e`
- `0x18001ca70`
- `0x18001f010`

## pseudocode

```c
void __fastcall Dock::UpdateProperties(Dock *this, char a2)
{
  __int64 v4; // rdx
  char v5; // r14
  char v6; // si
  int v7; // eax
  unsigned __int16 *v8; // rcx
  int v9; // eax
  char *v10; // r8
  char *v11; // rdx
  char *v12; // rax
  int AepProperties; // eax
  __int64 v14; // rdx
  unsigned int v15; // [rsp+38h] [rbp-C8h]
  unsigned int v16[4]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v17; // [rsp+60h] [rbp-A0h] BYREF
  struct _DEVPROPERTY v18; // [rsp+70h] [rbp-90h] BYREF
  char v19[2]; // [rsp+2B0h] [rbp+1B0h] BYREF

  if ( *((_QWORD *)this + 365) )
  {
    v17 = 0;
    memset_0(&v18, 0, 0x240u);
    v5 = *((_BYTE *)this + 586);
    v6 = *((_BYTE *)this + 2912);
    if ( *((_BYTE *)this + 587) )
    {
      DockingDevnodeHelpers::GetModelName((unsigned __int16 *)v19, v4, (Dock *)((char *)this + 1136));
      v7 = *((_DWORD *)this + 280);
      v8 = (unsigned __int16 *)((char *)this + 592);
      *(_QWORD *)v17.Data4 = 25995;
      *(_DWORD *)&v17.Data4[2] = v7;
      *(_WORD *)&v17.Data4[6] = *((_WORD *)this + 562);
      v17.Data1 = 835023776;
      *(_DWORD *)&v17.Data2 = 1232565745;
    }
    else if ( *((_BYTE *)this + 1744) )
    {
      DockingDevnodeHelpers::GetModelName((unsigned __int16 *)v19, v4, (Dock *)((char *)this + 2292));
      v9 = *((_DWORD *)this + 570);
      v8 = (unsigned __int16 *)((char *)this + 1752);
      *(_QWORD *)v17.Data4 = 25995;
      *(_DWORD *)&v17.Data4[2] = v9;
      *(_WORD *)&v17.Data4[6] = *((_WORD *)this + 1142);
      v17.Data1 = 835023776;
      *(_DWORD *)&v17.Data2 = 1232565745;
    }
    else
    {
      v8 = (unsigned __int16 *)&byte_18002145C;
      *(_WORD *)v19 = 0;
    }
    v10 = (char *)DockingDevnodeHelpers::DevPropTrue;
    v11 = (char *)DockingDevnodeHelpers::DevPropTrue;
    v12 = (char *)DockingDevnodeHelpers::DevPropTrue;
    if ( !v6 )
      v11 = (char *)DockingDevnodeHelpers::DevPropFalse;
    if ( !a2 )
      v12 = (char *)DockingDevnodeHelpers::DevPropFalse;
    if ( !v5 )
      v10 = (char *)DockingDevnodeHelpers::DevPropFalse;
    AepProperties = DockingDevnodeHelpers::GetAepProperties(
                      v8,
                      &v17,
                      v10,
                      v19,
                      v12,
                      v11,
                      (unsigned __int16 *)v19,
                      v15,
                      &v18,
                      v16);
    if ( AepProperties >= 0 )
    {
      if ( *((_QWORD *)this + 366) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
            (_DWORD)this,
            (__int64)this);
        }
        (*(void (__fastcall **)(_QWORD, __int64, struct _DEVPROPERTY *))(**((_QWORD **)this + 366) + 40LL))(
          *((_QWORD *)this + 366),
          12,
          &v18);
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids, this);
          }
          v14 = 1;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids, this);
          }
          v14 = 0;
        }
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 366) + 32LL))(*((_QWORD *)this + 366), v14);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
          (_DWORD)this,
          (__int64)this);
      }
      (*(void (__fastcall **)(_QWORD, __int64, struct _DEVPROPERTY *))(**((_QWORD **)this + 365) + 32LL))(
        *((_QWORD *)this + 365),
        12,
        &v18);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25)
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
        this,
        AepProperties);
    }
  }
}

```

## disassembly

```asm
0x180012ddc  push    rbp
0x180012dde  push    rbx
0x180012ddf  push    rsi
0x180012de0  push    rdi
0x180012de1  push    r14
0x180012de3  push    r15
0x180012de5  lea     rbp, [rsp-428h]
0x180012ded  sub     rsp, 528h
0x180012df4  mov     rax, cs:__security_cookie
0x180012dfb  xor     rax, rsp
0x180012dfe  mov     [rbp+450h+var_40], rax
0x180012e05  xor     r15d, r15d
0x180012e08  mov     dil, dl
0x180012e0b  mov     rbx, rcx
0x180012e0e  cmp     [rcx+0B68h], r15
0x180012e15  jz      loc_1800130ED
0x180012e1b  xorps   xmm0, xmm0
0x180012e1e  lea     rcx, [rsp+550h+var_4E0]; void *
0x180012e23  xor     edx, edx; Val
0x180012e25  mov     r8d, 240h; Size
0x180012e2b  movups  xmmword ptr [rsp+550h+var_4F0.Data1], xmm0
0x180012e30  call    memset_0
0x180012e35  mov     r14b, [rbx+24Ah]
0x180012e3c  mov     sil, [rbx+0B60h]
0x180012e43  cmp     [rbx+24Bh], r15b
0x180012e4a  jz      short loc_180012EA2
0x180012e4c  lea     r8, [rbx+470h]; struct _MANUFACTURER_INFO *
0x180012e53  lea     rcx, [rbp+450h+var_2A0]; Destination
0x180012e5a  call    ?GetModelName@DockingDevnodeHelpers@@SAXPEAG_KAEBU_MANUFACTURER_INFO@@@Z; DockingDevnodeHelpers::GetModelName(ushort *,unsigned __int64,_MANUFACTURER_INFO const &)
0x180012e5f  mov     eax, [rbx+460h]
0x180012e65  lea     rcx, [rbx+250h]
0x180012e6c  mov     qword ptr [rsp+550h+var_4F0.Data4], 658Bh
0x180012e75  mov     dword ptr [rsp+550h+var_4F0.Data4+2], eax
0x180012e79  movzx   eax, word ptr [rbx+464h]
0x180012e80  mov     word ptr [rsp+550h+var_4F0.Data4+6], ax
0x180012e85  mov     [rsp+550h+var_4F0.Data1], 31C573A0h
0x180012e8d  mov     dword ptr [rsp+550h+var_4F0.Data2], 497775F1h
0x180012e95  movaps  xmm0, xmmword ptr [rsp+550h+var_4F0.Data1]
0x180012e9a  movdqa  xmmword ptr [rsp+550h+var_4F0.Data1], xmm0
0x180012ea0  jmp     short loc_180012F10
0x180012ea2  cmp     [rbx+6D0h], r15b
0x180012ea9  jz      short loc_180012F01
0x180012eab  lea     r8, [rbx+8F4h]; struct _MANUFACTURER_INFO *
0x180012eb2  lea     rcx, [rbp+450h+var_2A0]; Destination
0x180012eb9  call    ?GetModelName@DockingDevnodeHelpers@@SAXPEAG_KAEBU_MANUFACTURER_INFO@@@Z; DockingDevnodeHelpers::GetModelName(ushort *,unsigned __int64,_MANUFACTURER_INFO const &)
0x180012ebe  mov     eax, [rbx+8E8h]
0x180012ec4  lea     rcx, [rbx+6D8h]
0x180012ecb  mov     qword ptr [rsp+550h+var_4F0.Data4], 658Bh
0x180012ed4  mov     dword ptr [rsp+550h+var_4F0.Data4+2], eax
0x180012ed8  movzx   eax, word ptr [rbx+8ECh]
0x180012edf  mov     word ptr [rsp+550h+var_4F0.Data4+6], ax
0x180012ee4  mov     [rsp+550h+var_4F0.Data1], 31C573A0h
0x180012eec  mov     dword ptr [rsp+550h+var_4F0.Data2], 497775F1h
0x180012ef4  movaps  xmm0, xmmword ptr [rsp+550h+var_4F0.Data1]
0x180012ef9  movdqa  xmmword ptr [rsp+550h+var_4F0.Data1], xmm0
0x180012eff  jmp     short loc_180012F10
0x180012f01  lea     rcx, byte_18002145C; unsigned __int16 *
0x180012f08  mov     word ptr [rbp+450h+var_2A0], r15w
0x180012f10  lea     r9, ?DevPropFalse@DockingDevnodeHelpers@@2DB; char const DockingDevnodeHelpers::DevPropFalse
0x180012f17  test    sil, sil
0x180012f1a  lea     r8, ?DevPropTrue@DockingDevnodeHelpers@@2DB; char const DockingDevnodeHelpers::DevPropTrue
0x180012f21  mov     rdx, r8
0x180012f24  mov     rax, r8
0x180012f27  cmovz   rdx, r9
0x180012f2b  test    dil, dil
0x180012f2e  cmovz   rax, r9
0x180012f32  test    r14b, r14b
0x180012f35  cmovz   r8, r9; char *
0x180012f39  lea     r9, [rsp+550h+var_500]
0x180012f3e  mov     [rsp+550h+var_508], r9; unsigned int *
0x180012f43  lea     r9, [rsp+550h+var_4E0]
0x180012f48  mov     [rsp+550h+var_510], r9; struct _DEVPROPERTY *
0x180012f4d  lea     r9, [rbp+450h+var_2A0]; char *
0x180012f54  mov     [rsp+550h+var_520], r9; unsigned __int16 *
0x180012f59  mov     [rsp+550h+var_528], rdx; char *
0x180012f5e  lea     rdx, [rsp+550h+var_4F0]; struct _GUID *
0x180012f63  mov     [rsp+550h+var_530], rax; char *
0x180012f68  call    ?GetAepProperties@DockingDevnodeHelpers@@SAJPEBGAEBU_GUID@@AEBD2220KPEAU_DEVPROPERTY@@PEAK@Z; DockingDevnodeHelpers::GetAepProperties(ushort const *,_GUID const &,char const &,char const &,char const &,char const &,ushort const *,ulong,_DEVPROPERTY *,ulong *)
0x180012f6d  test    eax, eax
0x180012f6f  jns     short loc_180012FBD
0x180012f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f78  lea     rdi, WPP_GLOBAL_Control
0x180012f7f  cmp     rcx, rdi
0x180012f82  jz      loc_1800130ED
0x180012f88  cmp     byte ptr [rcx+19h], 1
0x180012f8c  jb      loc_1800130ED
0x180012f92  test    byte ptr [rcx+1Ch], 1
0x180012f96  jz      loc_1800130ED
0x180012f9c  mov     rcx, [rcx+10h]
0x180012fa0  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012fa7  mov     edx, 11h
0x180012fac  mov     dword ptr [rsp+550h+var_530], eax
0x180012fb0  mov     r9, rbx
0x180012fb3  call    WPP_SF_qD
0x180012fb8  jmp     loc_1800130ED
0x180012fbd  lea     rdi, WPP_GLOBAL_Control
0x180012fc4  lea     rsi, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012fcb  cmp     [rbx+0B70h], r15
0x180012fd2  jz      loc_18001309F
0x180012fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fdf  cmp     rcx, rdi
0x180012fe2  jz      short loc_180013009
0x180012fe4  cmp     byte ptr [rcx+19h], 4
0x180012fe8  jb      short loc_180013009
0x180012fea  test    byte ptr [rcx+1Ch], 1
0x180012fee  jz      short loc_180013009
0x180012ff0  mov     rcx, [rcx+10h]
0x180012ff4  mov     edx, 12h
0x180012ff9  mov     r9, rbx
0x180012ffc  mov     [rsp+550h+var_530], rbx
0x180013001  mov     r8, rsi
0x180013004  call    WPP_SF_qS
0x180013009  mov     rcx, [rbx+0B70h]
0x180013010  lea     r8, [rsp+550h+var_4E0]
0x180013015  mov     edx, 0Ch
0x18001301a  mov     rax, [rcx]
0x18001301d  mov     rax, [rax+28h]
0x180013021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013026  test    r14b, r14b
0x180013029  jz      short loc_18001305E
0x18001302b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013032  cmp     rcx, rdi
0x180013035  jz      short loc_180013057
0x180013037  cmp     byte ptr [rcx+19h], 3
0x18001303b  jb      short loc_180013057
0x18001303d  test    byte ptr [rcx+1Ch], 1
0x180013041  jz      short loc_180013057
0x180013043  mov     rcx, [rcx+10h]
0x180013047  mov     edx, 13h
0x18001304c  mov     r9, rbx
0x18001304f  mov     r8, rsi
0x180013052  call    WPP_SF_q
0x180013057  mov     edx, 1
0x18001305c  jmp     short loc_18001308C
0x18001305e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013065  cmp     rcx, rdi
0x180013068  jz      short loc_18001308A
0x18001306a  cmp     byte ptr [rcx+19h], 3
0x18001306e  jb      short loc_18001308A
0x180013070  test    byte ptr [rcx+1Ch], 1
0x180013074  jz      short loc_18001308A
0x180013076  mov     rcx, [rcx+10h]
0x18001307a  mov     edx, 14h
0x18001307f  mov     r9, rbx
0x180013082  mov     r8, rsi
0x180013085  call    WPP_SF_q
0x18001308a  xor     edx, edx
0x18001308c  mov     rcx, [rbx+0B70h]
0x180013093  mov     rax, [rcx]
0x180013096  mov     rax, [rax+20h]
0x18001309a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001309f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130a6  cmp     rcx, rdi
0x1800130a9  jz      short loc_1800130D0
0x1800130ab  cmp     byte ptr [rcx+19h], 4
0x1800130af  jb      short loc_1800130D0
0x1800130b1  test    byte ptr [rcx+1Ch], 1
0x1800130b5  jz      short loc_1800130D0
0x1800130b7  mov     rcx, [rcx+10h]
0x1800130bb  mov     edx, 15h
0x1800130c0  mov     r9, rbx
0x1800130c3  mov     [rsp+550h+var_530], rbx
0x1800130c8  mov     r8, rsi
0x1800130cb  call    WPP_SF_qS
0x1800130d0  mov     rcx, [rbx+0B68h]
0x1800130d7  lea     r8, [rsp+550h+var_4E0]
0x1800130dc  mov     edx, 0Ch
0x1800130e1  mov     rax, [rcx]
0x1800130e4  mov     rax, [rax+20h]
0x1800130e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130ed  mov     rcx, [rbp+450h+var_40]
0x1800130f4  xor     rcx, rsp; StackCookie
0x1800130f7  call    __security_check_cookie
0x1800130fc  add     rsp, 528h
0x180013103  pop     r15
0x180013105  pop     r14
0x180013107  pop     rdi
0x180013108  pop     rsi
0x180013109  pop     rbx
0x18001310a  pop     rbp
0x18001310b  retn
```
