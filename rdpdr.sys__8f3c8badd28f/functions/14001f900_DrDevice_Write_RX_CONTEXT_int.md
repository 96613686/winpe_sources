# DrDevice::Write(_RX_CONTEXT *,int)

- ea: `0x14001f900`
- end: `0x14001fb8c`
- name: `?Write@DrDevice@@UEAAJPEAU_RX_CONTEXT@@H@Z`
- size: `652`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, struct _RX_CONTEXT *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x14001ec50`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x140001e30`
- `0x140003188`
- `0x14000327c`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x14001f900`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001faba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001faba`

## pseudocode

```c
__int64 __fastcall DrDevice::Write(DrDevice *this, struct _RX_CONTEXT *a2, int a3)
{
  RefCount *v3; // rax
  RefCount *v7; // rbx
  __int64 v8; // r9
  unsigned int v9; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebp
  char *v13; // rax
  char *v14; // rdi
  __int64 v15; // rcx
  PVOID v16; // rax
  unsigned int v17; // eax
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-48h]
  RefCount *v19; // [rsp+70h] [rbp+8h] BYREF
  RefCount *v20; // [rsp+78h] [rbp+10h] BYREF

  v3 = (RefCount *)*((_QWORD *)this + 4);
  v20 = v3;
  if ( v3 )
    RefCount::AddRef(v3);
  v7 = *(RefCount **)&a2->pFobx->OffsetOfNextEaToReturn;
  v19 = v7;
  if ( v7 )
    RefCount::AddRef(v7);
  if ( *((_DWORD *)v3 + 149) != 3 || !v7 )
    goto LABEL_11;
  v8 = *((unsigned int *)this + 14);
  if ( (_DWORD)v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v8);
LABEL_11:
    v9 = -1073741667;
    goto LABEL_12;
  }
  v11 = *((_DWORD *)&a2->9 + 42);
  if ( v11 )
  {
    v12 = v11 + 56;
    if ( v11 + 56 >= v11 && v12 >= 0x38 && (v13 = (char *)operator new(v12, 0x100u), (v14 = v13) != 0) )
    {
      memset(v13, 0, v12);
      *(_DWORD *)v14 = 1230128242;
      *((_DWORD *)v14 + 1) = *((_DWORD *)this + 10);
      *((_DWORD *)v14 + 2) = *((_DWORD *)v7 + 6);
      *((_QWORD *)v14 + 2) = 4;
      *((_DWORD *)v14 + 6) = *((_DWORD *)&a2->9 + 42);
      *(_QWORD *)(v14 + 28) = a2->Create.TransportName.Buffer;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
          *((unsigned int *)&a2->9 + 40));
      v15 = *((_QWORD *)&a2->9 + 18);
      if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
        v16 = *(PVOID *)(v15 + 24);
      else
        v16 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
      if ( v16 )
      {
        memmove(v14 + 56, v16, *((unsigned int *)v14 + 6));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
            *((unsigned int *)v14 + 6));
        LOBYTE(BugCheckOnFailure) = ((__int64)a2->RdbssDbgExtension & 0x1000) == 0;
        v17 = (*(__int64 (__fastcall **)(DrDevice *, struct _RX_CONTEXT *, char *, _QWORD, ULONG, union _LARGE_INTEGER *, int))(*(_QWORD *)this + 24LL))(
                this,
                a2,
                v14,
                v12,
                BugCheckOnFailure,
                &g_IOTimeOut,
                a3);
        v9 = v17;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v17);
      }
      else
      {
        v9 = -1073741670;
      }
      operator delete(v14);
    }
    else
    {
      v9 = -1073741670;
    }
  }
  else
  {
    a2->InformationToReturn = 0;
    v9 = 0;
  }
LABEL_12:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v19);
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v20);
  return v9;
}

```

## disassembly

```asm
0x14001f900  mov     [rsp+arg_10], rbx
0x14001f905  mov     [rsp+arg_18], rbp
0x14001f90a  push    rsi
0x14001f90b  push    rdi
0x14001f90c  push    r12
0x14001f90e  push    r14
0x14001f910  push    r15
0x14001f912  sub     rsp, 40h
0x14001f916  mov     rax, [rcx+20h]
0x14001f91a  mov     r12d, r8d
0x14001f91d  mov     [rsp+68h+arg_8], rax
0x14001f922  mov     rsi, rdx
0x14001f925  mov     r15, rcx
0x14001f928  test    rax, rax
0x14001f92b  jz      short loc_14001F935
0x14001f92d  mov     rcx, rax; this
0x14001f930  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001f935  mov     rbx, [rdx+40h]
0x14001f939  mov     rbx, [rbx+40h]
0x14001f93d  mov     [rsp+68h+arg_0], rbx
0x14001f942  test    rbx, rbx
0x14001f945  jz      short loc_14001F94F
0x14001f947  mov     rcx, rbx; this
0x14001f94a  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001f94f  cmp     dword ptr [rax+254h], 3
0x14001f956  jnz     short loc_14001F994
0x14001f958  test    rbx, rbx
0x14001f95b  jz      short loc_14001F994
0x14001f95d  mov     r9d, [r15+38h]
0x14001f961  test    r9d, r9d
0x14001f964  jz      short loc_14001F9C9
0x14001f966  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f96d  lea     r14, WPP_GLOBAL_Control
0x14001f974  cmp     rcx, r14
0x14001f977  jz      short loc_14001F994
0x14001f979  cmp     byte ptr [rcx+29h], 5
0x14001f97d  jb      short loc_14001F994
0x14001f97f  mov     rcx, [rcx+18h]
0x14001f983  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001f98a  mov     edx, 21h ; '!'
0x14001f98f  call    WPP_SF_d
0x14001f994  mov     ebx, 0C000009Dh
0x14001f999  lea     rcx, [rsp+68h+arg_0]
0x14001f99e  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f9a3  lea     rcx, [rsp+68h+arg_8]
0x14001f9a8  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001f9ad  lea     r11, [rsp+68h+var_28]
0x14001f9b2  mov     eax, ebx
0x14001f9b4  mov     rbx, [r11+40h]
0x14001f9b8  mov     rbp, [r11+48h]
0x14001f9bc  mov     rsp, r11
0x14001f9bf  pop     r15
0x14001f9c1  pop     r14
0x14001f9c3  pop     r12
0x14001f9c5  pop     rdi
0x14001f9c6  pop     rsi
0x14001f9c7  retn
0x14001f9c9  mov     eax, [rdx+238h]
0x14001f9cf  test    eax, eax
0x14001f9d1  jnz     short loc_14001F9E2
0x14001f9d3  mov     qword ptr [rdx+0B8h], 0
0x14001f9de  xor     ebx, ebx
0x14001f9e0  jmp     short loc_14001F999
0x14001f9e2  lea     ebp, [rax+38h]
0x14001f9e5  cmp     ebp, eax
0x14001f9e7  jb      loc_14001FB82
0x14001f9ed  cmp     ebp, 38h ; '8'
0x14001f9f0  jb      loc_14001FB82
0x14001f9f6  mov     edx, 100h; unsigned __int64
0x14001f9fb  mov     ecx, ebp; unsigned __int64
0x14001f9fd  mov     r14d, ebp
0x14001fa00  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001fa05  mov     rdi, rax
0x14001fa08  test    rax, rax
0x14001fa0b  jz      loc_14001FB82
0x14001fa11  mov     r8d, r14d; Size
0x14001fa14  xor     edx, edx; Val
0x14001fa16  mov     rcx, rax; void *
0x14001fa19  call    memset
0x14001fa1e  mov     dword ptr [rdi], 49524472h
0x14001fa24  mov     ecx, [r15+28h]
0x14001fa28  mov     [rdi+4], ecx
0x14001fa2b  mov     ecx, [rbx+18h]
0x14001fa2e  mov     [rdi+8], ecx
0x14001fa31  mov     qword ptr [rdi+10h], 4
0x14001fa39  mov     eax, [rsi+238h]
0x14001fa3f  mov     [rdi+18h], eax
0x14001fa42  mov     eax, [rsi+230h]
0x14001fa48  mov     [rdi+1Ch], eax
0x14001fa4b  mov     rax, [rsi+230h]
0x14001fa52  sar     rax, 20h
0x14001fa56  mov     [rdi+20h], eax
0x14001fa59  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa60  lea     r14, WPP_GLOBAL_Control
0x14001fa67  cmp     rcx, r14
0x14001fa6a  jz      short loc_14001FA8E
0x14001fa6c  cmp     byte ptr [rcx+29h], 5
0x14001fa70  jb      short loc_14001FA8E
0x14001fa72  mov     r9d, [rsi+230h]
0x14001fa79  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001fa80  mov     rcx, [rcx+18h]
0x14001fa84  mov     edx, 22h ; '"'
0x14001fa89  call    WPP_SF_d
0x14001fa8e  mov     rcx, [rsi+220h]; MemoryDescriptorList
0x14001fa95  test    byte ptr [rcx+0Ah], 5
0x14001fa99  jz      short loc_14001FAA1
0x14001fa9b  mov     rax, [rcx+18h]
0x14001fa9f  jmp     short loc_14001FAC6
0x14001faa1  xor     r9d, r9d; RequestedAddress
0x14001faa4  mov     [rsp+68h+Priority], 40000010h; Priority
0x14001faac  xor     edx, edx; AccessMode
0x14001faae  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001fab6  lea     r8d, [r9+1]; CacheType
0x14001faba  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001fac1  nop     dword ptr [rax+rax+00h]
0x14001fac6  test    rax, rax
0x14001fac9  jz      loc_14001FB70
0x14001facf  mov     r8d, [rdi+18h]; Size
0x14001fad3  lea     rcx, [rdi+38h]; void *
0x14001fad7  mov     rdx, rax; Src
0x14001fada  call    memmove
0x14001fadf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fae6  cmp     rcx, r14
0x14001fae9  jz      short loc_14001FB0A
0x14001faeb  cmp     byte ptr [rcx+29h], 5
0x14001faef  jb      short loc_14001FB0A
0x14001faf1  mov     r9d, [rdi+18h]
0x14001faf5  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001fafc  mov     rcx, [rcx+18h]
0x14001fb00  mov     edx, 23h ; '#'
0x14001fb05  call    WPP_SF_d
0x14001fb0a  mov     ecx, [rsi+78h]
0x14001fb0d  lea     rdx, ?g_IOTimeOut@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_IOTimeOut
0x14001fb14  mov     rax, [r15]
0x14001fb17  mov     r9d, ebp
0x14001fb1a  shr     ecx, 0Ch
0x14001fb1d  mov     r8, rdi
0x14001fb20  not     cl
0x14001fb22  mov     [rsp+68h+var_38], r12d
0x14001fb27  and     cl, 1
0x14001fb2a  mov     qword ptr [rsp+68h+Priority], rdx
0x14001fb2f  mov     rax, [rax+18h]
0x14001fb33  mov     rdx, rsi
0x14001fb36  mov     byte ptr [rsp+68h+BugCheckOnFailure], cl
0x14001fb3a  mov     rcx, r15
0x14001fb3d  call    _guard_dispatch_icall
0x14001fb42  mov     ebx, eax
0x14001fb44  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb4b  cmp     rcx, r14
0x14001fb4e  jz      short loc_14001FB75
0x14001fb50  cmp     byte ptr [rcx+29h], 4
0x14001fb54  jb      short loc_14001FB75
0x14001fb56  mov     rcx, [rcx+18h]
0x14001fb5a  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14001fb61  mov     edx, 24h ; '$'
0x14001fb66  mov     r9d, eax
0x14001fb69  call    WPP_SF_d
0x14001fb6e  jmp     short loc_14001FB75
0x14001fb70  mov     ebx, 0C000009Ah
0x14001fb75  mov     rcx, rdi; void *
0x14001fb78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001fb7d  jmp     loc_14001F999
0x14001fb82  mov     ebx, 0C000009Ah
0x14001fb87  jmp     loc_14001F999
```
