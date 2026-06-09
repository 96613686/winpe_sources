# DrDrive::NotifyChangeDirectory(_RX_CONTEXT *)

- ea: `0x1400125e0`
- end: `0x140012797`
- name: `?NotifyChangeDirectory@DrDrive@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(DrDrive *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x14000327c`
- `0x140006480`
- `0x140006560`
- `0x1400125e0`

## pseudocode

```c
__int64 __fastcall DrDrive::NotifyChangeDirectory(DrDrive *this, struct _RX_CONTEXT *a2)
{
  __int64 v2; // rax
  struct _RX_CONTEXT *v3; // r11
  DrDrive *v4; // r10
  RefCount *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r9
  int RdbssDbgExtension; // r8d
  __int64 (__fastcall *v10)(DrDrive *, struct _RX_CONTEXT *, __int128 *, __int64, bool, union _LARGE_INTEGER *, _DWORD); // rax
  RefCount *v11; // [rsp+40h] [rbp+7h] BYREF
  __int64 v12; // [rsp+48h] [rbp+Fh] BYREF
  __int128 v13; // [rsp+50h] [rbp+17h] BYREF
  __int128 v14; // [rsp+60h] [rbp+27h]
  __int128 v15; // [rsp+70h] [rbp+37h]
  __int64 v16; // [rsp+80h] [rbp+47h]

  v2 = *((_QWORD *)this + 4);
  v3 = a2;
  v12 = v2;
  v4 = this;
  if ( v2 )
    RefCount::AddRef((RefCount *)v2);
  v5 = *(RefCount **)&a2->pFobx->OffsetOfNextEaToReturn;
  v11 = v5;
  if ( v5 )
    RefCount::AddRef(v5);
  v13 = 0;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( (*(unsigned __int16 *)(v2 + 1134) | (*(unsigned __int16 *)(v2 + 1132) << 16)) - 65540 >= 0 )
  {
    if ( *(_DWORD *)(v2 + 596) == 3 && v5 )
    {
      v7 = *((unsigned int *)v4 + 14);
      if ( !(_DWORD)v7 )
      {
        RdbssDbgExtension = (int)v3->RdbssDbgExtension;
        DWORD1(v13) = *((_DWORD *)v4 + 10);
        LODWORD(v13) = 1230128242;
        DWORD2(v13) = *((_DWORD *)v5 + 6);
        BYTE8(v14) = *((_BYTE *)&v3->9 + 136);
        *(_DWORD *)((char *)&v14 + 9) = *((_DWORD *)&v3->9 + 35);
        v10 = *(__int64 (__fastcall **)(DrDrive *, struct _RX_CONTEXT *, __int128 *, __int64, bool, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)v4 + 24LL);
        *(_QWORD *)&v14 = 0x20000000CLL;
        v6 = v10(v4, v3, &v13, 56, (RdbssDbgExtension & 0x1000) == 0, &g_IOTimeOut, 0);
        goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v7);
    }
    v6 = -1073741667;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    v6 = -1073741822;
  }
LABEL_17:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v11);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v12);
  return v6;
}

```

## disassembly

```asm
0x1400125e0  mov     [rsp-8+arg_10], rbx
0x1400125e5  push    rbp
0x1400125e6  lea     rbp, [rsp-57h]
0x1400125eb  sub     rsp, 90h
0x1400125f2  mov     rax, cs:__security_cookie
0x1400125f9  xor     rax, rsp
0x1400125fc  mov     [rbp+57h+var_8], rax
0x140012600  mov     rax, [rcx+20h]
0x140012604  mov     r11, rdx
0x140012607  mov     [rbp+57h+var_48], rax
0x14001260b  mov     r10, rcx
0x14001260e  test    rax, rax
0x140012611  jz      short loc_14001261B
0x140012613  mov     rcx, rax; this
0x140012616  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001261b  mov     rcx, [rdx+40h]
0x14001261f  mov     rcx, [rcx+40h]; this
0x140012623  mov     [rbp+57h+var_50], rcx
0x140012627  test    rcx, rcx
0x14001262a  jz      short loc_140012631
0x14001262c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140012631  xorps   xmm0, xmm0
0x140012634  xor     edx, edx
0x140012636  movups  [rbp+57h+var_40], xmm0
0x14001263a  mov     [rbp+57h+var_10], rdx
0x14001263e  movups  [rbp+57h+var_30], xmm0
0x140012642  movups  [rbp+57h+var_20], xmm0
0x140012646  movzx   r8d, word ptr [rax+46Ch]
0x14001264e  movzx   edx, word ptr [rax+46Eh]
0x140012655  shl     r8d, 10h
0x140012659  or      r8d, edx
0x14001265c  cmp     r8d, 10004h
0x140012663  jns     short loc_14001269A
0x140012665  mov     rcx, cs:WPP_GLOBAL_Control
0x14001266c  lea     rax, WPP_GLOBAL_Control
0x140012673  cmp     rcx, rax
0x140012676  jz      short loc_140012693
0x140012678  cmp     byte ptr [rcx+29h], 5
0x14001267c  jb      short loc_140012693
0x14001267e  mov     rcx, [rcx+18h]
0x140012682  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012689  mov     edx, 2Dh ; '-'
0x14001268e  call    WPP_SF_
0x140012693  mov     ebx, 0C0000002h
0x140012698  jmp     short loc_1400126E4
0x14001269a  cmp     dword ptr [rax+254h], 3
0x1400126a1  jnz     short loc_1400126DF
0x1400126a3  test    rcx, rcx
0x1400126a6  jz      short loc_1400126DF
0x1400126a8  mov     r9d, [r10+38h]
0x1400126ac  test    r9d, r9d
0x1400126af  jz      short loc_140012716
0x1400126b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126b8  lea     rax, WPP_GLOBAL_Control
0x1400126bf  cmp     rcx, rax
0x1400126c2  jz      short loc_1400126DF
0x1400126c4  cmp     byte ptr [rcx+29h], 5
0x1400126c8  jb      short loc_1400126DF
0x1400126ca  mov     rcx, [rcx+18h]
0x1400126ce  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400126d5  mov     edx, 2Eh ; '.'
0x1400126da  call    WPP_SF_d
0x1400126df  mov     ebx, 0C000009Dh
0x1400126e4  lea     rcx, [rbp+57h+var_50]
0x1400126e8  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400126ed  lea     rcx, [rbp+57h+var_48]
0x1400126f1  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400126f6  mov     eax, ebx
0x1400126f8  mov     rcx, [rbp+57h+var_8]
0x1400126fc  xor     rcx, rsp; StackCookie
0x1400126ff  call    __security_check_cookie
0x140012704  mov     rbx, [rsp+90h+arg_10]
0x14001270c  add     rsp, 90h
0x140012713  pop     rbp
0x140012714  retn
0x140012716  mov     eax, [r10+28h]
0x14001271a  mov     r9d, 38h ; '8'
0x140012720  mov     r8d, [r11+78h]
0x140012724  mov     rdx, r11
0x140012727  mov     dword ptr [rbp+57h+var_40+4], eax
0x14001272a  shr     r8d, 0Ch
0x14001272e  not     r8b
0x140012731  mov     dword ptr [rbp+57h+var_40], 49524472h
0x140012738  mov     eax, [rcx+18h]
0x14001273b  and     r8b, 1
0x14001273f  mov     dword ptr [rbp+57h+var_40+8], eax
0x140012742  lea     rcx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x140012749  mov     al, [r11+218h]
0x140012750  mov     byte ptr [rbp+57h+var_30+8], al
0x140012753  mov     eax, [r11+21Ch]
0x14001275a  mov     dword ptr [rbp+57h+var_30+9], eax
0x14001275d  mov     rax, [r10]
0x140012760  mov     [rsp+90h+var_60], 0
0x140012768  mov     [rsp+90h+var_68], rcx
0x14001276d  mov     rcx, r10
0x140012770  mov     [rsp+90h+var_70], r8b
0x140012775  lea     r8, [rbp+57h+var_40]
0x140012779  mov     rax, [rax+18h]
0x14001277d  mov     dword ptr [rbp+57h+var_30], 0Ch
0x140012784  mov     dword ptr [rbp+57h+var_30+4], 2
0x14001278b  call    _guard_dispatch_icall
0x140012790  mov     ebx, eax
0x140012792  jmp     loc_1400126E4
```
