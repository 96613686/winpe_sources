# DrDevice::Read(_RX_CONTEXT *)

- ea: `0x14001f710`
- end: `0x14001f8d6`
- name: `?Read@DrDevice@@QEAAJPEAU_RX_CONTEXT@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140017bf0`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000327c`
- `0x14000589c`
- `0x140006480`
- `0x140006560`
- `0x14001f710`

## pseudocode

```c
__int64 __fastcall DrDevice::Read(DrDevice *this, struct _RX_CONTEXT *a2)
{
  RefCount *v2; // rax
  RefCount *v5; // rcx
  __int64 v6; // r9
  unsigned int v7; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // edx
  unsigned int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-29h]
  RefCount *v13; // [rsp+40h] [rbp-9h] BYREF
  RefCount *v14; // [rsp+48h] [rbp-1h] BYREF
  __int128 v15; // [rsp+50h] [rbp+7h] BYREF
  __int128 v16; // [rsp+60h] [rbp+17h]
  __int128 v17; // [rsp+70h] [rbp+27h]
  __int64 v18; // [rsp+80h] [rbp+37h]

  v2 = (RefCount *)*((_QWORD *)this + 4);
  v14 = v2;
  if ( v2 )
    RefCount::AddRef(v2);
  v5 = *(RefCount **)&a2->pFobx->OffsetOfNextEaToReturn;
  v13 = v5;
  if ( v5 )
    RefCount::AddRef(v5);
  v15 = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( *((_DWORD *)v2 + 149) != 3 || !v5 )
    goto LABEL_11;
  v6 = *((unsigned int *)this + 14);
  if ( (_DWORD)v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v6);
LABEL_11:
    v7 = -1073741667;
    goto LABEL_12;
  }
  v9 = *((_DWORD *)&a2->9 + 42);
  v10 = *((_DWORD *)&a2->9 + 40);
  DWORD1(v15) = *((_DWORD *)this + 10);
  LODWORD(v15) = 1230128242;
  DWORD2(v15) = *((_DWORD *)v5 + 6);
  LODWORD(v17) = HIDWORD(a2->Create.TransportName.Buffer);
  *(_QWORD *)&v16 = 3;
  *((_QWORD *)&v16 + 1) = __PAIR64__(v10, v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v12 = v10;
    WPP_SF_lD(WPP_GLOBAL_Control->AttachedDevice);
  }
  LOBYTE(v12) = ((__int64)a2->RdbssDbgExtension & 0x1000) == 0;
  v11 = (*(__int64 (__fastcall **)(DrDevice *, struct _RX_CONTEXT *, __int128 *, __int64, unsigned int, union _LARGE_INTEGER *, _DWORD))(*(_QWORD *)this + 24LL))(
          this,
          a2,
          &v15,
          56,
          v12,
          &g_IOTimeOut,
          0);
  v7 = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v11);
LABEL_12:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v13);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v14);
  return v7;
}

```

## disassembly

```asm
0x14001f710  mov     [rsp-8+arg_10], rbx
0x14001f715  push    rbp
0x14001f716  push    rsi
0x14001f717  push    rdi
0x14001f718  lea     rbp, [rsp-47h]
0x14001f71d  sub     rsp, 90h
0x14001f724  mov     rax, cs:__security_cookie
0x14001f72b  xor     rax, rsp
0x14001f72e  mov     [rbp+57h+var_18], rax
0x14001f732  mov     rax, [rcx+20h]
0x14001f736  mov     rsi, rdx
0x14001f739  mov     [rbp+57h+var_58], rax
0x14001f73d  mov     rbx, rcx
0x14001f740  test    rax, rax
0x14001f743  jz      short loc_14001F74D
0x14001f745  mov     rcx, rax; this
0x14001f748  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001f74d  mov     rcx, [rdx+40h]
0x14001f751  mov     rcx, [rcx+40h]; this
0x14001f755  mov     [rbp+57h+var_60], rcx
0x14001f759  test    rcx, rcx
0x14001f75c  jz      short loc_14001F763
0x14001f75e  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001f763  xorps   xmm0, xmm0
0x14001f766  xor     edx, edx
0x14001f768  movups  [rbp+57h+var_50], xmm0
0x14001f76c  mov     [rbp+57h+var_20], rdx
0x14001f770  movups  [rbp+57h+var_40], xmm0
0x14001f774  movups  [rbp+57h+var_30], xmm0
0x14001f778  cmp     dword ptr [rax+254h], 3
0x14001f77f  jnz     short loc_14001F7BD
0x14001f781  test    rcx, rcx
0x14001f784  jz      short loc_14001F7BD
0x14001f786  mov     r9d, [rbx+38h]
0x14001f78a  test    r9d, r9d
0x14001f78d  jz      short loc_14001F7F6
0x14001f78f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f796  lea     rdi, WPP_GLOBAL_Control
0x14001f79d  cmp     rcx, rdi
0x14001f7a0  jz      short loc_14001F7BD
0x14001f7a2  cmp     byte ptr [rcx+29h], 5
0x14001f7a6  jb      short loc_14001F7BD
0x14001f7a8  mov     rcx, [rcx+18h]
0x14001f7ac  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f7b3  mov     edx, 25h ; '%'
0x14001f7b8  call    WPP_SF_d
0x14001f7bd  mov     ebx, 0C000009Dh
0x14001f7c2  lea     rcx, [rbp+57h+var_60]
0x14001f7c6  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f7cb  lea     rcx, [rbp+57h+var_58]
0x14001f7cf  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f7d4  mov     eax, ebx
0x14001f7d6  mov     rcx, [rbp+57h+var_18]
0x14001f7da  xor     rcx, rsp; StackCookie
0x14001f7dd  call    __security_check_cookie
0x14001f7e2  mov     rbx, [rsp+0A0h+arg_10]
0x14001f7ea  add     rsp, 90h
0x14001f7f1  pop     rdi
0x14001f7f2  pop     rsi
0x14001f7f3  pop     rbp
0x14001f7f4  retn
0x14001f7f6  mov     eax, [rbx+28h]
0x14001f7f9  mov     r9d, [rsi+238h]
0x14001f800  mov     edx, [rsi+230h]
0x14001f806  mov     dword ptr [rbp+57h+var_50+4], eax
0x14001f809  mov     dword ptr [rbp+57h+var_50], 49524472h
0x14001f810  mov     eax, [rcx+18h]
0x14001f813  mov     dword ptr [rbp+57h+var_50+8], eax
0x14001f816  mov     rax, [rsi+230h]
0x14001f81d  sar     rax, 20h
0x14001f821  mov     dword ptr [rbp+57h+var_30], eax
0x14001f824  mov     qword ptr [rbp+57h+var_40], 3
0x14001f82c  mov     dword ptr [rbp+57h+var_40+8], r9d
0x14001f830  mov     dword ptr [rbp+57h+var_40+0Ch], edx
0x14001f833  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f83a  lea     rdi, WPP_GLOBAL_Control
0x14001f841  cmp     rcx, rdi
0x14001f844  jz      short loc_14001F859
0x14001f846  cmp     byte ptr [rcx+29h], 4
0x14001f84a  jb      short loc_14001F859
0x14001f84c  mov     rcx, [rcx+18h]
0x14001f850  mov     [rsp+0A0h+var_80], edx
0x14001f854  call    WPP_SF_lD
0x14001f859  mov     r8d, [rsi+78h]
0x14001f85d  lea     rcx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x14001f864  mov     rax, [rbx]
0x14001f867  mov     r9d, 38h ; '8'
0x14001f86d  shr     r8d, 0Ch
0x14001f871  mov     rdx, rsi
0x14001f874  not     r8b
0x14001f877  mov     [rsp+0A0h+var_70], 0
0x14001f87f  and     r8b, 1
0x14001f883  mov     [rsp+0A0h+var_78], rcx
0x14001f888  mov     rax, [rax+18h]
0x14001f88c  mov     rcx, rbx
0x14001f88f  mov     byte ptr [rsp+0A0h+var_80], r8b
0x14001f894  lea     r8, [rbp+57h+var_50]
0x14001f898  call    _guard_dispatch_icall
0x14001f89d  mov     ebx, eax
0x14001f89f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8a6  cmp     rcx, rdi
0x14001f8a9  jz      loc_14001F7C2
0x14001f8af  cmp     byte ptr [rcx+29h], 4
0x14001f8b3  jb      loc_14001F7C2
0x14001f8b9  mov     rcx, [rcx+18h]
0x14001f8bd  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f8c4  mov     edx, 27h ; '''
0x14001f8c9  mov     r9d, eax
0x14001f8cc  call    WPP_SF_d
0x14001f8d1  jmp     loc_14001F7C2
```
