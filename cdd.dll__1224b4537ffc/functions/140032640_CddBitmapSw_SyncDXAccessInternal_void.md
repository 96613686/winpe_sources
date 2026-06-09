# CddBitmapSw::SyncDXAccessInternal(void)

- ea: `0x140032640`
- end: `0x1400326d9`
- name: `?SyncDXAccessInternal@CddBitmapSw@@UEAAXXZ`
- size: `153`
- prototype: `void __fastcall(CddBitmapSw *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000e35c`
- `0x140015570`
- `0x1400190c4`
- `0x140032640`
- `0x1400372d0`

## pseudocode

```c
void __fastcall CddBitmapSw::SyncDXAccessInternal(CddBitmapSw *this)
{
  __int64 v2; // rax
  struct CDDPDEV *v3; // rdx
  _QWORD v4[3]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v5; // [rsp+38h] [rbp-38h] BYREF
  __int128 v6; // [rsp+48h] [rbp-28h]
  __int128 v7; // [rsp+58h] [rbp-18h]

  if ( *((_DWORD *)this + 10) )
  {
    v2 = *((_QWORD *)this + 1);
    v5 = 0;
    v4[0] = 0;
    v6 = 0;
    v4[2] = 0;
    v7 = 0;
    if ( (*(unsigned int (__fastcall **)(CddBitmapSw *))(v2 + 80))(this) )
    {
      v3 = (struct CDDPDEV *)*((_QWORD *)this + 1);
      v5 = 0;
      LODWORD(v5) = (_DWORD)this;
      v6 = 0;
      v7 = 0;
      CDDETWPROFILERSTARTEND::IssueStart((CDDETWPROFILERSTARTEND *)v4, v3, 0xBECu, (struct _DXGKETW_PARAMS *)&v5);
    }
    CDDPDEV::SyncGPUAccess(*((CDDPDEV **)this + 1), *((_DWORD *)this + 10), 1u);
    CDDETWPROFILERSTARTEND::~CDDETWPROFILERSTARTEND((CDDETWPROFILERSTARTEND *)v4);
  }
}

```

## disassembly

```asm
0x140032640  mov     [rsp-8+arg_0], rbx
0x140032645  push    rbp
0x140032646  mov     rbp, rsp
0x140032649  sub     rsp, 70h
0x14003264d  cmp     dword ptr [rcx+28h], 0
0x140032651  mov     rbx, rcx
0x140032654  jz      short loc_1400326CA
0x140032656  mov     rax, [rcx+8]
0x14003265a  xorps   xmm0, xmm0
0x14003265d  movups  [rbp+var_38], xmm0
0x140032661  mov     [rbp+var_50], 0
0x140032669  movups  [rbp+var_28], xmm0
0x14003266d  mov     [rbp+var_40], 0
0x140032675  movups  [rbp+var_18], xmm0
0x140032679  mov     rax, [rax+50h]
0x14003267d  call    _guard_dispatch_icall
0x140032682  test    eax, eax
0x140032684  jz      short loc_1400326AF
0x140032686  mov     rdx, [rbx+8]; struct CDDPDEV *
0x14003268a  lea     r9, [rbp+var_38]; struct _DXGKETW_PARAMS *
0x14003268e  xorps   xmm0, xmm0
0x140032691  lea     rcx, [rbp+var_50]; this
0x140032695  movups  [rbp+var_38], xmm0
0x140032699  mov     r8d, 0BECh; unsigned int
0x14003269f  mov     dword ptr [rbp+var_38], ebx
0x1400326a2  movups  [rbp+var_28], xmm0
0x1400326a6  movups  [rbp+var_18], xmm0
0x1400326aa  call    ?IssueStart@CDDETWPROFILERSTARTEND@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@@Z; CDDETWPROFILERSTARTEND::IssueStart(CDDPDEV *,uint,_DXGKETW_PARAMS *)
0x1400326af  mov     edx, [rbx+28h]; unsigned int
0x1400326b2  mov     r8d, 1; int
0x1400326b8  mov     rcx, [rbx+8]; this
0x1400326bc  call    ?SyncGPUAccess@CDDPDEV@@QEAAJIH@Z; CDDPDEV::SyncGPUAccess(uint,int)
0x1400326c1  lea     rcx, [rbp+var_50]; this
0x1400326c5  call    ??1CDDETWPROFILERSTARTEND@@QEAA@XZ; CDDETWPROFILERSTARTEND::~CDDETWPROFILERSTARTEND(void)
0x1400326ca  mov     rbx, [rsp+70h+arg_0]
0x1400326d2  add     rsp, 70h
0x1400326d6  pop     rbp
0x1400326d7  retn
```
