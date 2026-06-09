# FCPostCreate

- ea: `0x140011fe0`
- end: `0x1400122da`
- name: `FCPostCreate`
- size: `762`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002fd0`
- `0x14000d1a8`
- `0x1400101c0`
- `0x140011fe0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012247`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140012247`
- `FLTMGR!FltSetStreamContext` at `0x1400121a6`
- `FLTMGR!FltSetStreamContext` at `0x1400121a6`
- `FLTMGR!FltCancelFileOpen` at `0x1400122a1`
- `FLTMGR!FltCancelFileOpen` at `0x1400122a1`
- `FLTMGR!FltGetStreamContext` at `0x140012054`
- `FLTMGR!FltGetStreamContext` at `0x140012054`
- `FLTMGR!FltIsDirectory` at `0x1400120ac`
- `FLTMGR!FltIsDirectory` at `0x1400120ac`
- `FLTMGR!FltReleaseContext` at `0x1400121d0`
- `FLTMGR!FltReleaseContext` at `0x140012258`
- `FLTMGR!FltReleaseContext` at `0x140012272`
- `FLTMGR!FltReleaseContext` at `0x140013872`
- `FLTMGR!FltReleaseContext` at `0x14001388f`
- `FLTMGR!FltReleaseContext` at `0x1400121d0`
- `FLTMGR!FltReleaseContext` at `0x140012258`
- `FLTMGR!FltReleaseContext` at `0x140012272`
- `FLTMGR!FltReleaseContext` at `0x140013872`
- `FLTMGR!FltReleaseContext` at `0x14001388f`
- `FLTMGR!FltAllocateContext` at `0x14001211d`
- `FLTMGR!FltAllocateContext` at `0x14001211d`
- `FLTMGR!FltGetVolumeContext` at `0x1400120e1`
- `FLTMGR!FltGetVolumeContext` at `0x1400120e1`

## pseudocode

```c
__int64 __fastcall FCPostCreate(__int64 a1, __int64 a2, _DWORD *a3, char a4)
{
  NTSTATUS StreamContext; // ebx
  void *v8; // rdi
  char v9; // r15
  char v10; // r12
  int v11; // eax
  _OWORD *v12; // rax
  NTSTATUS v13; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // [rsp+34h] [rbp-44h]
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-40h] BYREF
  PFLT_CONTEXT v19; // [rsp+40h] [rbp-38h] BYREF
  void *v20; // [rsp+48h] [rbp-30h]
  unsigned __int8 IsDirectory; // [rsp+90h] [rbp+18h] BYREF

  v19 = 0;
  Context = 0;
  StreamContext = 0;
  v8 = 0;
  v20 = 0;
  v17 = 1;
  v9 = 0;
  v10 = 0;
  IsDirectory = 0;
  if ( a3 )
  {
    v8 = *(void **)a3;
    v20 = *(void **)a3;
    v17 = a3[2];
    v10 = *((_BYTE *)a3 + 12);
    ExFreeToNPagedLookasideList(&gPre2PostCreateContextList, a3);
  }
  v11 = *(_DWORD *)(a1 + 24);
  if ( v11 < 0 || v11 == 260 )
  {
    if ( v11 == -1073741772 && v10 )
      *(_DWORD *)(a1 + 24) = -1073741790;
    v9 = 1;
  }
  else if ( (a4 & 1) == 0 )
  {
    StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
    if ( StreamContext < 0 )
    {
      if ( v8 )
      {
        StreamContext = FltIsDirectory(*(PFILE_OBJECT *)(a2 + 32), *(PFLT_INSTANCE *)(a2 + 24), &IsDirectory);
        if ( StreamContext >= 0 && !IsDirectory )
        {
          StreamContext = FltGetVolumeContext(*(PFLT_FILTER *)(a2 + 8), *(PFLT_VOLUME *)(a2 + 16), &v19);
          if ( StreamContext >= 0 )
          {
            StreamContext = FltAllocateContext(gFilterHandle, 8u, 0x28u, (POOL_TYPE)512, &Context);
            if ( StreamContext >= 0 )
            {
              v12 = Context;
              *(_OWORD *)Context = 0;
              v12[1] = 0;
              *((_QWORD *)v12 + 4) = 0;
              *((_QWORD *)Context + 3) = v8;
              *((_DWORD *)Context + 8) = v17;
              v8 = 0;
              v20 = 0;
              StreamContext = FCpEncStreamStart((char *)v19 + 24, *((_QWORD *)Context + 3), v17, Context);
              if ( StreamContext >= 0 )
              {
                v13 = FltSetStreamContext(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        *(PFILE_OBJECT *)(a2 + 32),
                        FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                        Context,
                        0);
                StreamContext = v13;
                if ( v13 == -1071906814 )
                {
                  StreamContext = 0;
                }
                else if ( v13 >= 0 )
                {
                  FltReleaseContext(Context);
                  Context = 0;
                }
              }
            }
          }
        }
      }
      else
      {
        StreamContext = 0;
      }
    }
  }
  if ( v19 )
  {
    FltReleaseContext(v19);
    v19 = 0;
  }
  if ( Context )
  {
    FltReleaseContext(Context);
    Context = 0;
  }
  if ( v8 )
    FCpFreeChamberId(v8);
  if ( !v9 && StreamContext < 0 )
  {
    FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    *(_DWORD *)(a1 + 24) = StreamContext;
    *(_QWORD *)(a1 + 32) = 0;
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0d_EtwWriteTransfer(v15, PostCreateFailure, v16, (unsigned int)StreamContext);
  }
  return 0;
}

```

## disassembly

```asm
0x140011fe0  mov     r11, rsp
0x140011fe3  mov     [r11+8], rbx
0x140011fe7  mov     [r11+10h], rsi
0x140011feb  push    rdi
0x140011fec  push    r12
0x140011fee  push    r13
0x140011ff0  push    r14
0x140011ff2  push    r15
0x140011ff4  sub     rsp, 50h
0x140011ff8  mov     esi, r9d
0x140011ffb  mov     r14, rdx
0x140011ffe  mov     r13, rcx
0x140012001  xor     eax, eax
0x140012003  mov     [r11-38h], rax
0x140012007  mov     [r11-40h], rax
0x14001200b  mov     ebx, eax
0x14001200d  mov     edi, eax
0x14001200f  mov     [r11-30h], rax
0x140012013  mov     [rsp+78h+var_44], 1
0x14001201b  xor     r15b, r15b
0x14001201e  xor     r12b, r12b
0x140012021  mov     [r11+18h], al
0x140012025  test    r8, r8
0x140012028  jnz     loc_140012228
0x14001202e  mov     eax, [r13+18h]
0x140012032  test    eax, eax
0x140012034  js      short loc_14001207E
0x140012036  cmp     eax, 104h
0x14001203b  jz      short loc_14001207E
0x14001203d  test    sil, 1
0x140012041  jnz     loc_1400121E1
0x140012047  lea     r8, [rsp+78h+Context]; Context
0x14001204c  mov     rdx, [r14+20h]; FileObject
0x140012050  mov     rcx, [r14+18h]; Instance
0x140012054  call    cs:__imp_FltGetStreamContext
0x14001205b  nop     dword ptr [rax+rax+00h]
0x140012060  mov     ebx, eax
0x140012062  mov     [rsp+78h+var_48], eax
0x140012066  test    eax, eax
0x140012068  jns     loc_1400121E1
0x14001206e  test    rdi, rdi
0x140012071  jnz     short loc_14001209C
0x140012073  xor     ebx, ebx
0x140012075  mov     [rsp+78h+var_48], ebx
0x140012079  jmp     loc_1400121E1
0x14001207e  cmp     eax, 0C0000034h
0x140012083  jz      short loc_14001208D
0x140012085  mov     r15b, 1
0x140012088  jmp     loc_1400121E1
0x14001208d  test    r12b, r12b
0x140012090  jz      short loc_140012085
0x140012092  mov     dword ptr [r13+18h], 0C0000022h
0x14001209a  jmp     short loc_140012085
0x14001209c  lea     r8, [rsp+78h+IsDirectory]; IsDirectory
0x1400120a4  mov     rdx, [r14+18h]; Instance
0x1400120a8  mov     rcx, [r14+20h]; FileObject
0x1400120ac  call    cs:__imp_FltIsDirectory
0x1400120b3  nop     dword ptr [rax+rax+00h]
0x1400120b8  mov     ebx, eax
0x1400120ba  mov     [rsp+78h+var_48], eax
0x1400120be  test    eax, eax
0x1400120c0  js      loc_1400121E1
0x1400120c6  cmp     [rsp+78h+IsDirectory], 0
0x1400120ce  jnz     loc_1400121E1
0x1400120d4  lea     r8, [rsp+78h+var_38]; Context
0x1400120d9  mov     rdx, [r14+10h]; Volume
0x1400120dd  mov     rcx, [r14+8]; Filter
0x1400120e1  call    cs:__imp_FltGetVolumeContext
0x1400120e8  nop     dword ptr [rax+rax+00h]
0x1400120ed  mov     ebx, eax
0x1400120ef  mov     [rsp+78h+var_48], eax
0x1400120f3  test    eax, eax
0x1400120f5  js      loc_1400121E1
0x1400120fb  mov     edx, 8; ContextType
0x140012100  lea     rax, [rsp+78h+Context]
0x140012105  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14001210a  mov     r9d, 200h; PoolType
0x140012110  mov     r8d, 28h ; '('; ContextSize
0x140012116  mov     rcx, cs:gFilterHandle; Filter
0x14001211d  call    cs:__imp_FltAllocateContext
0x140012124  nop     dword ptr [rax+rax+00h]
0x140012129  mov     ebx, eax
0x14001212b  mov     [rsp+78h+var_48], eax
0x14001212f  test    eax, eax
0x140012131  js      loc_1400121E1
0x140012137  xorps   xmm0, xmm0
0x14001213a  xor     ecx, ecx
0x14001213c  mov     rax, [rsp+78h+Context]
0x140012141  movups  xmmword ptr [rax], xmm0
0x140012144  movups  xmmword ptr [rax+10h], xmm0
0x140012148  mov     [rax+20h], rcx
0x14001214c  mov     rax, [rsp+78h+Context]
0x140012151  mov     [rax+18h], rdi
0x140012155  mov     rax, [rsp+78h+Context]
0x14001215a  mov     r8d, [rsp+78h+var_44]
0x14001215f  mov     [rax+20h], r8d
0x140012163  xor     edi, edi
0x140012165  mov     [rsp+78h+var_30], rdi
0x14001216a  mov     rcx, [rsp+78h+var_38]
0x14001216f  add     rcx, 18h
0x140012173  mov     rdx, [rsp+78h+Context]
0x140012178  mov     r9, rdx
0x14001217b  mov     rdx, [rdx+18h]
0x14001217f  call    FCpEncStreamStart
0x140012184  mov     ebx, eax
0x140012186  mov     [rsp+78h+var_48], eax
0x14001218a  test    eax, eax
0x14001218c  js      short loc_1400121E1
0x14001218e  mov     [rsp+78h+ReturnedContext], rdi; OldContext
0x140012193  mov     r9, [rsp+78h+Context]; NewContext
0x140012198  mov     r8d, 1; Operation
0x14001219e  mov     rdx, [r14+20h]; FileObject
0x1400121a2  mov     rcx, [r14+18h]; Instance
0x1400121a6  call    cs:__imp_FltSetStreamContext
0x1400121ad  nop     dword ptr [rax+rax+00h]
0x1400121b2  mov     ebx, eax
0x1400121b4  mov     [rsp+78h+var_48], eax
0x1400121b8  cmp     eax, 0C01C0002h
0x1400121bd  jnz     short loc_1400121C7
0x1400121bf  xor     ebx, ebx
0x1400121c1  mov     [rsp+78h+var_48], ebx
0x1400121c5  jmp     short loc_1400121E1
0x1400121c7  test    eax, eax
0x1400121c9  js      short loc_1400121E1
0x1400121cb  mov     rcx, [rsp+78h+Context]; Context
0x1400121d0  call    cs:__imp_FltReleaseContext
0x1400121d7  nop     dword ptr [rax+rax+00h]
0x1400121dc  mov     [rsp+78h+Context], rdi
0x1400121e1  mov     rcx, [rsp+78h+var_38]; Context
0x1400121e6  test    rcx, rcx
0x1400121e9  jnz     short loc_140012258
0x1400121eb  mov     rcx, [rsp+78h+Context]; Context
0x1400121f0  test    rcx, rcx
0x1400121f3  jnz     short loc_140012272
0x1400121f5  test    rdi, rdi
0x1400121f8  jnz     loc_14001228C
0x1400121fe  test    r15b, r15b
0x140012201  jnz     short loc_14001220B
0x140012203  test    ebx, ebx
0x140012205  js      loc_140012299
0x14001220b  xor     eax, eax
0x14001220d  lea     r11, [rsp+78h+var_28]
0x140012212  mov     rbx, [r11+30h]
0x140012216  mov     rsi, [r11+38h]
0x14001221a  mov     rsp, r11
0x14001221d  pop     r15
0x14001221f  pop     r14
0x140012221  pop     r13
0x140012223  pop     r12
0x140012225  pop     rdi
0x140012226  retn
0x140012228  mov     rdi, [r8]
0x14001222b  mov     [rsp+78h+var_30], rdi
0x140012230  mov     eax, [r8+8]
0x140012234  mov     [rsp+78h+var_44], eax
0x140012238  movzx   r12d, byte ptr [r8+0Ch]
0x14001223d  mov     rdx, r8; Entry
0x140012240  lea     rcx, gPre2PostCreateContextList; Lookaside
0x140012247  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001224e  nop     dword ptr [rax+rax+00h]
0x140012253  jmp     loc_14001202E
0x140012258  call    cs:__imp_FltReleaseContext
0x14001225f  nop     dword ptr [rax+rax+00h]
0x140012264  mov     [rsp+78h+var_38], 0
0x14001226d  jmp     loc_1400121EB
0x140012272  call    cs:__imp_FltReleaseContext
0x140012279  nop     dword ptr [rax+rax+00h]
0x14001227e  mov     [rsp+78h+Context], 0
0x140012287  jmp     loc_1400121F5
0x14001228c  mov     rcx, rdi; P
0x14001228f  call    FCpFreeChamberId
0x140012294  jmp     loc_1400121FE
0x140012299  mov     rdx, [r14+20h]; FileObject
0x14001229d  mov     rcx, [r14+18h]; Instance
0x1400122a1  call    cs:__imp_FltCancelFileOpen
0x1400122a8  nop     dword ptr [rax+rax+00h]
0x1400122ad  mov     [r13+18h], ebx
0x1400122b1  mov     qword ptr [r13+20h], 0
0x1400122b9  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 2
0x1400122c0  jz      loc_14001220B
0x1400122c6  mov     r9d, ebx
0x1400122c9  lea     rdx, PostCreateFailure
0x1400122d0  call    McTemplateK0d_EtwWriteTransfer
0x1400122d5  jmp     loc_14001220B
0x140013860  push    rbp
0x140013862  sub     rsp, 30h
0x140013866  mov     rbp, rdx
0x140013869  mov     rcx, [rbp+40h]; Context
0x14001386d  test    rcx, rcx
0x140013870  jz      short loc_140013886
0x140013872  call    cs:__imp_FltReleaseContext
0x140013879  nop     dword ptr [rax+rax+00h]
0x14001387e  mov     qword ptr [rbp+40h], 0
0x140013886  mov     rcx, [rbp+38h]; Context
0x14001388a  test    rcx, rcx
0x14001388d  jz      short loc_1400138A3
0x14001388f  call    cs:__imp_FltReleaseContext
0x140013896  nop     dword ptr [rax+rax+00h]
0x14001389b  mov     qword ptr [rbp+38h], 0
0x1400138a3  mov     rcx, [rbp+48h]; P
0x1400138a7  test    rcx, rcx
0x1400138aa  jz      short loc_1400138B2
0x1400138ac  call    FCpFreeChamberId
0x1400138b1  nop
0x1400138b2  add     rsp, 30h
0x1400138b6  pop     rbp
0x1400138b7  retn
```
