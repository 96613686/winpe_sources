# FltpCreateFileNameInformationWorker

- ea: `0x180058e80`
- end: `0x180059212`
- name: `FltpCreateFileNameInformationWorker`
- size: `914`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180019920`

## callees

- `0x180009f20`
- `0x1800148b0`
- `0x180024880`
- `0x180057fe0`
- `0x180058e80`
- `0x180059220`
- `0x180059470`
- `0x18005a2e0`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180059117`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059117`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180058ec6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180058ec6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180058f72`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180058f72`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180058ff8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180058ff8`

## string_xrefs

- `0x180058f3c`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180059071`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x1800590a8`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x1800591b0`: `FltpCreateFileNameInformationWorker`
- `0x1800591d6`: `FltpCreateFileNameInformationWorker`
- `0x1800591ef`: `FltpCreateFileNameInformationWorker`

## pseudocode

```c
__int64 __fastcall FltpCreateFileNameInformationWorker(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rcx
  _DWORD *v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  int NormalizedFileName; // eax
  int FileNameInformation; // esi
  __int64 v9; // rdi
  int v10; // eax
  int v12; // eax
  __int64 v13; // rax
  int OpenedFileName; // ebp
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rcx
  __int64 v23; // rcx
  char v24; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  if ( v1 )
    v3 = *(_QWORD *)(v1 + 16);
  else
    v3 = 0;
  *(_QWORD *)(a1 + 136) = v3;
  *(_QWORD *)(a1 + 144) = _InterlockedExchangeAdd64(&qword_18003FDD0, 0);
  v4 = ExAllocateFromNPagedLookasideList(&stru_18003EDC0);
  *(_QWORD *)(a1 + 112) = v4;
  v5 = (__int64)v4;
  if ( !v4 )
  {
    FileNameInformation = -1073741670;
    goto LABEL_12;
  }
  v4[4] = 0;
  v4[6] = 0;
  v4[5] = 254;
  *(_OWORD *)v4 = 0;
  *((_WORD *)v4 + 1) = 254;
  *((_QWORD *)v4 + 1) = v4 + 7;
  v6 = (unsigned __int8)*(_DWORD *)(a1 + 108);
  if ( v6 == 1 )
  {
    if ( (byte_1800404C3 & 4) != 0 )
      McTemplateU0sp_EtwWriteTransfer(
        v5,
        (__int64)NameCacheSup_c3791,
        "FltpCreateFileNameInformationWorker",
        *(_QWORD *)(a1 + 64));
    NormalizedFileName = FltpGetNormalizedFileName(a1);
  }
  else
  {
    v12 = v6 - 2;
    if ( !v12 )
    {
      if ( (byte_1800404C3 & 4) != 0 )
        McTemplateU0sp_EtwWriteTransfer(
          v5,
          (__int64)NameCacheSup_c3800,
          "FltpCreateFileNameInformationWorker",
          *(_QWORD *)(a1 + 64));
      v13 = *(_QWORD *)(a1 + 48);
      v24 = 0;
      if ( v13 )
      {
        v15 = *(_QWORD *)(a1 + 80);
        v16 = 0;
        if ( v15 )
        {
          v17 = *(_QWORD *)(v15 + 16);
          v16 = *(_QWORD *)(v17 + 16);
          *(_QWORD *)(v17 + 16) = *(_QWORD *)(v13 + 16);
        }
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)(a1 + 48) + 24LL))(
                *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL),
                *(_QWORD *)(a1 + 64),
                *(_QWORD *)(a1 + 80),
                *(unsigned int *)(a1 + 108),
                &v24,
                *(_QWORD *)(a1 + 112));
        OpenedFileName = v18;
        if ( (unsigned __int8)*(_DWORD *)(a1 + 108) == 1 )
        {
          if ( (int)FltpDbgStatus(v18) < 0 )
          {
            if ( OpenedFileName != -1073741670 )
            {
              *(_DWORD *)(a1 + 40) |= 0x2000u;
              if ( (*(_DWORD *)(a1 + 40) & 0x4000) != 0 )
                OpenedFileName = -1071906811;
              else
                OpenedFileName = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)(a1 + 48) + 24LL))(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL),
                                   *(_QWORD *)(a1 + 64),
                                   *(_QWORD *)(a1 + 80),
                                   *(_DWORD *)(a1 + 108) & 0xFFFFFF00 | 2,
                                   &v24,
                                   *(_QWORD *)(a1 + 112));
            }
          }
          else
          {
            *(_DWORD *)(a1 + 40) |= 0x1000u;
          }
        }
        v19 = *(_QWORD *)(a1 + 80);
        if ( v19 )
          *(_QWORD *)(*(_QWORD *)(v19 + 16) + 16LL) = v16;
        if ( (int)FltpDbgStatus(OpenedFileName) >= 0 )
        {
          if ( v24 )
            *(_DWORD *)(a1 + 40) |= 2u;
          v20 = *(_QWORD *)(a1 + 24);
          if ( v20 )
            v21 = *(_DWORD *)(v20 + 56);
          else
            v21 = **(_DWORD **)(a1 + 32);
          if ( (v21 & 1) != 0 )
          {
            v22 = *(_QWORD *)(a1 + 24);
            if ( v22 )
              v23 = v22 + 112;
            else
              v23 = *(_QWORD *)(a1 + 32) + 8LL;
            FltpParseShareName(v23, *(_QWORD *)(a1 + 112));
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 + 40) |= 2u;
        OpenedFileName = FltpGetOpenedFileName(a1);
      }
      FileNameInformation = OpenedFileName;
      goto LABEL_9;
    }
    if ( v12 != 1 )
    {
      FileNameInformation = -1073741811;
      goto LABEL_12;
    }
    if ( (byte_1800404C3 & 4) != 0 )
      McTemplateU0sp_EtwWriteTransfer(
        v5,
        (__int64)NameCacheSup_c3810,
        "FltpCreateFileNameInformationWorker",
        *(_QWORD *)(a1 + 64));
    NormalizedFileName = FltpCallShortFileNameHandler(a1);
  }
  FileNameInformation = NormalizedFileName;
LABEL_9:
  if ( FileNameInformation >= 0 )
  {
    FileNameInformation = FltpAllocateFileNameInformation(a1);
    if ( (int)FltpDbgStatus(FileNameInformation) >= 0 )
      FileNameInformation = 0;
  }
LABEL_12:
  v9 = *(_QWORD *)(a1 + 112);
  if ( v9 )
  {
    v10 = *(_DWORD *)(v9 + 16);
    if ( (v10 & 1) != 0 )
    {
      if ( (v10 & 2) != 0 )
      {
        ExFreeToPagedLookasideList(&stru_18003F440, *(PVOID *)(v9 + 8));
        *(_DWORD *)(v9 + 16) &= ~2u;
      }
      else
      {
        ExFreePoolWithTag(*(PVOID *)(v9 + 8), 0x346E4D46u);
      }
      *(_DWORD *)(v9 + 16) &= ~1u;
    }
    ExFreeToNPagedLookasideList(&stru_18003EDC0, *(PVOID *)(a1 + 112));
    *(_QWORD *)(a1 + 112) = 0;
  }
  return (unsigned int)FileNameInformation;
}

```

## disassembly

```asm
0x180058e80  push    rbx
0x180058e82  push    rdi
0x180058e83  push    r15
0x180058e85  sub     rsp, 40h
0x180058e89  mov     rax, [rcx+30h]
0x180058e8d  xor     r15d, r15d
0x180058e90  mov     rbx, rcx
0x180058e93  test    rax, rax
0x180058e96  jz      loc_180058FDA
0x180058e9c  mov     rcx, [rax+10h]
0x180058ea0  mov     [rsp+58h+arg_10], rsi
0x180058ea5  mov     rax, r15
0x180058ea8  mov     [rbx+88h], rcx
0x180058eaf  lock xadd cs:qword_18003FDD0, rax
0x180058eb8  lea     rcx, stru_18003EDC0; Lookaside
0x180058ebf  mov     [rbx+90h], rax
0x180058ec6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180058ecd  nop     dword ptr [rax+rax+00h]
0x180058ed2  mov     [rbx+70h], rax
0x180058ed6  mov     rcx, rax
0x180058ed9  test    rax, rax
0x180058edc  jz      loc_180059100
0x180058ee2  mov     [rax+10h], r15d
0x180058ee6  xorps   xmm0, xmm0
0x180058ee9  mov     [rax+18h], r15d
0x180058eed  mov     eax, 0FEh
0x180058ef2  mov     [rcx+14h], eax
0x180058ef5  movups  xmmword ptr [rcx], xmm0
0x180058ef8  mov     [rcx+2], ax
0x180058efc  lea     rax, [rcx+1Ch]
0x180058f00  mov     [rcx+8], rax
0x180058f04  mov     eax, [rbx+6Ch]
0x180058f07  movzx   eax, al
0x180058f0a  cmp     eax, 1
0x180058f0d  jnz     loc_180058F93
0x180058f13  test    cs:byte_1800404C3, 4
0x180058f1a  jnz     loc_1800591AC
0x180058f20  mov     rcx, rbx
0x180058f23  call    FltpGetNormalizedFileName
0x180058f28  mov     esi, eax
0x180058f2a  test    esi, esi
0x180058f2c  js      short loc_180058F57
0x180058f2e  mov     rcx, rbx
0x180058f31  call    FltpAllocateFileNameInformation
0x180058f36  mov     r8d, 0EFDh
0x180058f3c  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180058f43  xor     r9d, r9d
0x180058f46  mov     ecx, eax
0x180058f48  mov     esi, eax
0x180058f4a  call    FltpDbgStatus
0x180058f4f  test    eax, eax
0x180058f51  jns     loc_18005910A
0x180058f57  mov     rdi, [rbx+70h]
0x180058f5b  test    rdi, rdi
0x180058f5e  jz      short loc_180058F82
0x180058f60  mov     eax, [rdi+10h]
0x180058f63  test    al, 1
0x180058f65  jnz     short loc_180058FE2
0x180058f67  mov     rdx, [rbx+70h]; Entry
0x180058f6b  lea     rcx, stru_18003EDC0; Lookaside
0x180058f72  call    cs:__imp_ExFreeToNPagedLookasideList
0x180058f79  nop     dword ptr [rax+rax+00h]
0x180058f7e  mov     [rbx+70h], r15
0x180058f82  mov     eax, esi
0x180058f84  mov     rsi, [rsp+58h+arg_10]
0x180058f89  add     rsp, 40h
0x180058f8d  pop     r15
0x180058f8f  pop     rdi
0x180058f90  pop     rbx
0x180058f91  retn
0x180058f93  sub     eax, 2
0x180058f96  jnz     loc_180059191
0x180058f9c  test    cs:byte_1800404C3, 4
0x180058fa3  mov     [rsp+58h+arg_8], rbp
0x180058fa8  jnz     loc_1800591EB
0x180058fae  mov     rax, [rbx+30h]
0x180058fb2  lea     rsi, [rbx+6Ch]
0x180058fb6  mov     [rsp+58h+arg_0], r15b
0x180058fbb  test    rax, rax
0x180058fbe  jnz     short loc_180059011
0x180058fc0  or      dword ptr [rbx+28h], 2
0x180058fc4  mov     rcx, rbx
0x180058fc7  call    FltpGetOpenedFileName
0x180058fcc  mov     ebp, eax
0x180058fce  mov     esi, ebp
0x180058fd0  mov     rbp, [rsp+58h+arg_8]
0x180058fd5  jmp     loc_180058F2A
0x180058fda  mov     rcx, r15
0x180058fdd  jmp     loc_180058EA0
0x180058fe2  mov     rcx, [rdi+8]; P
0x180058fe6  test    al, 2
0x180058fe8  jz      loc_180059112
0x180058fee  mov     rdx, rcx; Entry
0x180058ff1  lea     rcx, stru_18003F440; Lookaside
0x180058ff8  call    cs:__imp_ExFreeToPagedLookasideList
0x180058fff  nop     dword ptr [rax+rax+00h]
0x180059004  and     dword ptr [rdi+10h], 0FFFFFFFDh
0x180059008  and     dword ptr [rdi+10h], 0FFFFFFFEh
0x18005900c  jmp     loc_180058F67
0x180059011  mov     rcx, [rbx+50h]
0x180059015  mov     [rsp+58h+arg_18], r14
0x18005901a  mov     r14, r15
0x18005901d  test    rcx, rcx
0x180059020  jz      short loc_180059032
0x180059022  mov     rcx, [rcx+10h]
0x180059026  mov     rax, [rax+10h]
0x18005902a  mov     r14, [rcx+10h]
0x18005902e  mov     [rcx+10h], rax
0x180059032  mov     rcx, [rbx+30h]
0x180059036  mov     rdx, [rbx+70h]
0x18005903a  mov     r9d, [rbx+6Ch]
0x18005903e  mov     r8, [rbx+50h]
0x180059042  mov     rax, [rcx+18h]
0x180059046  mov     rcx, [rcx+10h]
0x18005904a  mov     [rsp+58h+var_30], rdx
0x18005904f  lea     rdx, [rsp+58h+arg_0]
0x180059054  mov     [rsp+58h+var_38], rdx
0x180059059  mov     rdx, [rbx+40h]
0x18005905d  call    _guard_dispatch_icall
0x180059062  mov     ecx, [rsi]
0x180059064  mov     ebp, eax
0x180059066  cmp     cl, 1
0x180059069  jnz     short loc_180059091
0x18005906b  mov     r8d, 197Eh
0x180059071  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x180059078  xor     r9d, r9d
0x18005907b  mov     ecx, eax
0x18005907d  call    FltpDbgStatus
0x180059082  test    eax, eax
0x180059084  js      loc_180059128
0x18005908a  or      dword ptr [rbx+28h], 1000h
0x180059091  mov     rax, [rbx+50h]
0x180059095  test    rax, rax
0x180059098  jz      short loc_1800590A2
0x18005909a  mov     rax, [rax+10h]
0x18005909e  mov     [rax+10h], r14
0x1800590a2  mov     r8d, 19B7h
0x1800590a8  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x1800590af  xor     r9d, r9d
0x1800590b2  mov     ecx, ebp
0x1800590b4  call    FltpDbgStatus
0x1800590b9  mov     r14, [rsp+58h+arg_18]
0x1800590be  test    eax, eax
0x1800590c0  js      loc_180058FCE
0x1800590c6  cmp     [rsp+58h+arg_0], r15b
0x1800590cb  jz      short loc_1800590D1
0x1800590cd  or      dword ptr [rbx+28h], 2
0x1800590d1  mov     rax, [rbx+18h]
0x1800590d5  test    rax, rax
0x1800590d8  jz      loc_180059207
0x1800590de  mov     ecx, [rax+38h]
0x1800590e1  test    cl, 1
0x1800590e4  jz      loc_180058FCE
0x1800590ea  mov     rcx, [rbx+18h]
0x1800590ee  test    rcx, rcx
0x1800590f1  jz      loc_18007931A
0x1800590f7  add     rcx, 70h ; 'p'
0x1800590fb  jmp     loc_180079322
0x180059100  mov     esi, 0C000009Ah
0x180059105  jmp     loc_180058F57
0x18005910a  mov     esi, r15d
0x18005910d  jmp     loc_180058F57
0x180059112  mov     edx, 346E4D46h; Tag
0x180059117  call    cs:__imp_ExFreePoolWithTag
0x18005911e  nop     dword ptr [rax+rax+00h]
0x180059123  jmp     loc_180059008
0x180059128  mov     esi, 0C000009Ah
0x18005912d  cmp     ebp, esi
0x18005912f  jz      loc_180059091
0x180059135  or      dword ptr [rbx+28h], 2000h
0x18005913c  test    dword ptr [rbx+28h], 4000h
0x180059143  jnz     short loc_180059187
0x180059145  mov     rcx, [rbx+30h]
0x180059149  mov     rdx, [rbx+70h]
0x18005914d  mov     r9d, [rbx+6Ch]
0x180059151  mov     r8, [rbx+50h]
0x180059155  and     r9d, 0FFFFFF02h
0x18005915c  mov     rax, [rcx+18h]
0x180059160  or      r9d, 2
0x180059164  mov     rcx, [rcx+10h]
0x180059168  mov     [rsp+58h+var_30], rdx
0x18005916d  lea     rdx, [rsp+58h+arg_0]
0x180059172  mov     [rsp+58h+var_38], rdx
0x180059177  mov     rdx, [rbx+40h]
0x18005917b  call    _guard_dispatch_icall
0x180059180  mov     ebp, eax
0x180059182  jmp     loc_180059091
0x180059187  mov     ebp, 0C01C0005h
0x18005918c  jmp     loc_180059091
0x180059191  cmp     eax, 1
0x180059194  jnz     short loc_1800591C8
0x180059196  test    cs:byte_1800404C3, 4
0x18005919d  jnz     short loc_1800591D2
0x18005919f  mov     rcx, rbx
0x1800591a2  call    FltpCallShortFileNameHandler
0x1800591a7  jmp     loc_180058F28
0x1800591ac  mov     r9, [rbx+40h]
0x1800591b0  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x1800591b7  lea     rdx, NameCacheSup_c3791
0x1800591be  call    McTemplateU0sp_EtwWriteTransfer
0x1800591c3  jmp     loc_180058F20
0x1800591c8  mov     esi, 0C000000Dh
0x1800591cd  jmp     loc_180058F57
0x1800591d2  mov     r9, [rbx+40h]
0x1800591d6  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x1800591dd  lea     rdx, NameCacheSup_c3810
0x1800591e4  call    McTemplateU0sp_EtwWriteTransfer
0x1800591e9  jmp     short loc_18005919F
0x1800591eb  mov     r9, [rbx+40h]
0x1800591ef  lea     r8, aFltpcreatefile; "FltpCreateFileNameInformationWorker"
0x1800591f6  lea     rdx, NameCacheSup_c3800
0x1800591fd  call    McTemplateU0sp_EtwWriteTransfer
0x180059202  jmp     loc_180058FAE
0x180059207  mov     rax, [rbx+20h]
0x18005920b  mov     ecx, [rax]
0x18005920d  jmp     loc_1800590E1
0x18007931a  mov     rcx, [rbx+20h]
0x18007931e  add     rcx, 8
0x180079322  mov     rdx, [rbx+70h]
0x180079326  call    FltpParseShareName
0x18007932b  nop
0x18007932c  jmp     loc_180058FCE
```
