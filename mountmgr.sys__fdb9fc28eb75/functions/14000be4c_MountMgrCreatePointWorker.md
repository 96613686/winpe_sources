# MountMgrCreatePointWorker

- ea: `0x14000be4c`
- end: `0x14000c2cb`
- name: `MountMgrCreatePointWorker`
- size: `1151`
- prototype: `__int64 __fastcall(_QWORD *Context, UNICODE_STRING *, __int64)`
- caller_count: `4`
- callee_count: `15`
- tags: `reparse_path, registry_config`

## callers

- `0x14000bcac`
- `0x14000fcc0`
- `0x14001045c`
- `0x140019af0`

## callees

- `0x140001730`
- `0x1400019c0`
- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x14000b588`
- `0x14000bbe4`
- `0x14000be4c`
- `0x140017540`
- `0x140018cd0`
- `0x140018da0`
- `0x140019140`
- `0x140019ca0`
- `0x14001a2b0`
- `0x14001a3d0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14000bfcc`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000bfcc`
- `ntoskrnl!PsIsHostSilo` at `0x14000c148`
- `ntoskrnl!PsIsHostSilo` at `0x14000c148`
- `ntoskrnl!ExAllocatePool2` at `0x14000be94`
- `ntoskrnl!ExAllocatePool2` at `0x14000c022`
- `ntoskrnl!ExAllocatePool2` at `0x14000c085`
- `ntoskrnl!ExAllocatePool2` at `0x14000be94`
- `ntoskrnl!ExAllocatePool2` at `0x14000c022`
- `ntoskrnl!ExAllocatePool2` at `0x14000c085`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c28b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c28b`

## string_xrefs

- `0x14000bfa9`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrCreatePointWorker(_QWORD *Context, UNICODE_STRING *a2, __int64 a3)
{
  WCHAR *Pool2; // rax
  WCHAR *v6; // r12
  __int64 v8; // r8
  NTSTATUS v9; // ebx
  __int64 v10; // r8
  unsigned __int16 *v11; // r14
  __int64 v12; // r8
  _WORD *v13; // rdi
  unsigned __int16 Length; // ax
  void *v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rcx
  WCHAR v18; // cx
  _BYTE *i; // rdi
  UNICODE_STRING Src; // [rsp+30h] [rbp-18h] BYREF

  Src = *a2;
  MountmgrSetDLStringCase(&Src);
  Pool2 = (WCHAR *)ExAllocatePool2(258, Src.Length + 2LL, 1098149453);
  v6 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, Src.Buffer, Src.Length);
    v6[(unsigned __int64)Src.Length >> 1] = 0;
    Src.MaximumLength += 2;
    Src.Buffer = v6;
    if ( (unsigned __int8)IsDriveLetter(&Src) && (unsigned __int8)HasDriveLetter(a3, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 110, v8, 0);
      v9 = -1073741811;
    }
    else
    {
      v9 = GlobalCreateSymbolicLink(&Src, a3 + 80);
      if ( v9 >= 0 )
      {
        v11 = *(unsigned __int16 **)(a3 + 96);
        v9 = RtlWriteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", v6, 3u, v11 + 1, *v11);
        if ( v9 >= 0 )
        {
          v13 = (_WORD *)ExAllocatePool2(258, 40, 1098149453);
          if ( v13 )
          {
            Length = Src.Length;
            v13[12] = Src.Length;
            Length += 2;
            v13[13] = Length;
            v15 = (void *)ExAllocatePool2(258, Length, 1098149453);
            *((_QWORD *)v13 + 4) = v15;
            if ( v15 )
            {
              memmove(v15, Src.Buffer, Src.Length);
              *(_WORD *)(*((_QWORD *)v13 + 4) + 2 * ((unsigned __int64)(unsigned __int16)v13[12] >> 1)) = 0;
              *((_BYTE *)v13 + 16) = 1;
              v16 = *(_QWORD **)(a3 + 24);
              if ( *v16 != a3 + 16 )
                __fastfail(3u);
              *(_QWORD *)v13 = a3 + 16;
              *((_QWORD *)v13 + 1) = v16;
              *v16 = v13;
              *(_QWORD *)(a3 + 24) = v13;
              if ( (unsigned __int8)PsIsHostSilo(Context[46]) )
                SendLinkCreated(v17, v13 + 12);
              if ( (unsigned __int8)IsDriveLetter(&Src) )
              {
                DeleteNoDriveLetterEntry(v11);
                if ( !*(_BYTE *)(a3 + 133) )
                  PostOnlineNotification(Context, a3 + 64);
              }
              if ( (Src.Length == 96 || Src.Length == 98 && Src.Buffer[48] == 92) && *Src.Buffer == 92 )
              {
                v18 = Src.Buffer[1];
                if ( (v18 == 63 || v18 == 92)
                  && Src.Buffer[2] == 63
                  && Src.Buffer[3] == 92
                  && Src.Buffer[4] == 86
                  && Src.Buffer[5] == 111
                  && Src.Buffer[6] == 108
                  && Src.Buffer[7] == 117
                  && Src.Buffer[8] == 109
                  && Src.Buffer[9] == 101
                  && Src.Buffer[10] == 123
                  && Src.Buffer[19] == 45
                  && Src.Buffer[24] == 45
                  && Src.Buffer[29] == 45
                  && Src.Buffer[34] == 45
                  && Src.Buffer[47] == 125
                  && Src.Length == 96
                  && v18 == 63
                  && *((_BYTE *)Context + 144) )
                {
                  for ( i = (_BYTE *)Context[2]; i != (_BYTE *)(Context + 2); i = *(_BYTE **)i )
                  {
                    if ( i[132] )
                      ReconcileThisDatabaseWithMaster(Context);
                  }
                }
              }
              ExFreePoolWithTag(v6, 0);
              MountMgrNotify(Context);
              if ( !*(_BYTE *)(a3 + 129) )
                MountMgrNotifyNameChange(Context, a3 + 80, 0);
              return (unsigned int)v9;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114);
            }
            ExFreePoolWithTag(v13, 0);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113);
          }
          GlobalDeleteSymbolicLink(&Src);
          v9 = -1073741670;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 112, v12, (unsigned int)v9);
          }
          GlobalDeleteSymbolicLink(&Src);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 111, v10, (unsigned int)v9);
      }
    }
    ExFreePoolWithTag(v6, 0);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 109);
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000be4c  push    rbp
0x14000be4e  push    rbx
0x14000be4f  push    rsi
0x14000be50  push    rdi
0x14000be51  push    r12
0x14000be53  push    r13
0x14000be55  push    r14
0x14000be57  push    r15
0x14000be59  mov     rbp, rsp
0x14000be5c  sub     rsp, 48h
0x14000be60  movups  xmm0, xmmword ptr [rdx]
0x14000be63  mov     rsi, rcx
0x14000be66  mov     r15, r8
0x14000be69  lea     rcx, [rbp+Src]
0x14000be6d  movdqu  xmmword ptr [rbp+Src.Length], xmm0
0x14000be72  call    MountmgrSetDLStringCase
0x14000be77  movzx   edx, [rbp+Src.Length]
0x14000be7b  mov     ebx, 2
0x14000be80  mov     edi, 41746E4Dh
0x14000be85  mov     r13d, 102h
0x14000be8b  add     rdx, rbx
0x14000be8e  mov     r8d, edi
0x14000be91  mov     ecx, r13d
0x14000be94  call    cs:__imp_ExAllocatePool2
0x14000be9b  nop     dword ptr [rax+rax+00h]
0x14000bea0  mov     r12, rax
0x14000bea3  test    rax, rax
0x14000bea6  jnz     short loc_14000BED8
0x14000bea8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000beaf  lea     rax, WPP_GLOBAL_Control
0x14000beb6  cmp     rcx, rax
0x14000beb9  jz      short loc_14000BECE
0x14000bebb  mov     eax, [rcx+2Ch]
0x14000bebe  test    al, 4
0x14000bec0  jz      short loc_14000BECE
0x14000bec2  mov     rcx, [rcx+18h]
0x14000bec6  lea     edx, [rbx+6Bh]
0x14000bec9  call    WPP_SF_
0x14000bece  mov     eax, 0C000009Ah
0x14000bed3  jmp     loc_14000C2B9
0x14000bed8  movzx   r8d, [rbp+Src.Length]; Size
0x14000bedd  mov     rcx, r12; void *
0x14000bee0  mov     rdx, [rbp+Src.Buffer]; Src
0x14000bee4  call    memmove
0x14000bee9  movzx   ecx, [rbp+Src.Length]
0x14000beed  xor     eax, eax
0x14000beef  shr     rcx, 1
0x14000bef2  mov     [r12+rcx*2], ax
0x14000bef7  lea     rcx, [rbp+Src]; String2
0x14000befb  add     [rbp+Src.MaximumLength], bx
0x14000beff  mov     [rbp+Src.Buffer], r12
0x14000bf03  call    IsDriveLetter
0x14000bf08  test    al, al
0x14000bf0a  jz      short loc_14000BF4F
0x14000bf0c  xor     edx, edx
0x14000bf0e  mov     rcx, r15
0x14000bf11  call    HasDriveLetter
0x14000bf16  test    al, al
0x14000bf18  jz      short loc_14000BF4F
0x14000bf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf21  lea     rax, WPP_GLOBAL_Control
0x14000bf28  cmp     rcx, rax
0x14000bf2b  jz      short loc_14000BF45
0x14000bf2d  mov     eax, [rcx+2Ch]
0x14000bf30  test    al, 1
0x14000bf32  jz      short loc_14000BF45
0x14000bf34  mov     rcx, [rcx+18h]
0x14000bf38  mov     edx, 6Eh ; 'n'
0x14000bf3d  xor     r9d, r9d
0x14000bf40  call    WPP_SF_L
0x14000bf45  mov     ebx, 0C000000Dh
0x14000bf4a  jmp     loc_14000C0E1
0x14000bf4f  lea     rdx, [r15+50h]
0x14000bf53  lea     rcx, [rbp+Src]
0x14000bf57  call    GlobalCreateSymbolicLink
0x14000bf5c  mov     ebx, eax
0x14000bf5e  test    eax, eax
0x14000bf60  jns     short loc_14000BFA5
0x14000bf62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf69  lea     rax, WPP_GLOBAL_Control
0x14000bf70  cmp     rcx, rax
0x14000bf73  jz      loc_14000C0E1
0x14000bf79  mov     edx, [rcx+2Ch]
0x14000bf7c  test    dl, 1
0x14000bf7f  jz      loc_14000C0E1
0x14000bf85  cmp     byte ptr [rcx+29h], 1
0x14000bf89  jb      loc_14000C0E1
0x14000bf8f  mov     rcx, [rcx+18h]
0x14000bf93  mov     edx, 6Fh ; 'o'
0x14000bf98  mov     r9d, ebx
0x14000bf9b  call    WPP_SF_L
0x14000bfa0  jmp     loc_14000C0E1
0x14000bfa5  mov     r14, [r15+60h]
0x14000bfa9  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000bfb0  mov     r9d, 3; ValueType
0x14000bfb6  mov     r8, r12; ValueName
0x14000bfb9  movzx   eax, word ptr [r14]
0x14000bfbd  lea     rcx, [r14+2]
0x14000bfc1  mov     [rsp+48h+ValueLength], eax; ValueLength
0x14000bfc5  mov     [rsp+48h+ValueData], rcx; ValueData
0x14000bfca  xor     ecx, ecx; RelativeTo
0x14000bfcc  call    cs:__imp_RtlWriteRegistryValue
0x14000bfd3  nop     dword ptr [rax+rax+00h]
0x14000bfd8  mov     ebx, eax
0x14000bfda  test    eax, eax
0x14000bfdc  jns     short loc_14000C017
0x14000bfde  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bfe5  lea     rax, WPP_GLOBAL_Control
0x14000bfec  cmp     rcx, rax
0x14000bfef  jz      short loc_14000C009
0x14000bff1  mov     eax, [rcx+2Ch]
0x14000bff4  test    al, 1
0x14000bff6  jz      short loc_14000C009
0x14000bff8  mov     rcx, [rcx+18h]
0x14000bffc  mov     edx, 70h ; 'p'
0x14000c001  mov     r9d, ebx
0x14000c004  call    WPP_SF_L
0x14000c009  lea     rcx, [rbp+Src]
0x14000c00d  call    GlobalDeleteSymbolicLink
0x14000c012  jmp     loc_14000C0E1
0x14000c017  mov     r8d, edi
0x14000c01a  mov     edx, 28h ; '('
0x14000c01f  mov     rcx, r13
0x14000c022  call    cs:__imp_ExAllocatePool2
0x14000c029  nop     dword ptr [rax+rax+00h]
0x14000c02e  mov     rdi, rax
0x14000c031  test    rax, rax
0x14000c034  jnz     short loc_14000C062
0x14000c036  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c03d  lea     rax, WPP_GLOBAL_Control
0x14000c044  cmp     rcx, rax
0x14000c047  jz      loc_14000C0D3
0x14000c04d  mov     eax, [rcx+2Ch]
0x14000c050  test    al, 4
0x14000c052  jz      short loc_14000C0D3
0x14000c054  mov     rcx, [rcx+18h]
0x14000c058  lea     edx, [rdi+71h]
0x14000c05b  call    WPP_SF_
0x14000c060  jmp     short loc_14000C0D3
0x14000c062  movzx   eax, [rbp+Src.Length]
0x14000c066  lea     r13, [rdi+18h]
0x14000c06a  mov     [r13+0], ax
0x14000c06f  mov     ecx, 102h
0x14000c074  add     ax, 2
0x14000c078  mov     r8d, 41746E4Dh
0x14000c07e  movzx   edx, ax
0x14000c081  mov     [rdi+1Ah], dx
0x14000c085  call    cs:__imp_ExAllocatePool2
0x14000c08c  nop     dword ptr [rax+rax+00h]
0x14000c091  mov     [rdi+20h], rax
0x14000c095  test    rax, rax
0x14000c098  jnz     short loc_14000C0F7
0x14000c09a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0a1  lea     rax, WPP_GLOBAL_Control
0x14000c0a8  cmp     rcx, rax
0x14000c0ab  jz      short loc_14000C0C2
0x14000c0ad  mov     eax, [rcx+2Ch]
0x14000c0b0  test    al, 4
0x14000c0b2  jz      short loc_14000C0C2
0x14000c0b4  mov     rcx, [rcx+18h]
0x14000c0b8  mov     edx, 72h ; 'r'
0x14000c0bd  call    WPP_SF_
0x14000c0c2  xor     edx, edx; Tag
0x14000c0c4  mov     rcx, rdi; P
0x14000c0c7  call    cs:__imp_ExFreePoolWithTag
0x14000c0ce  nop     dword ptr [rax+rax+00h]
0x14000c0d3  lea     rcx, [rbp+Src]
0x14000c0d7  call    GlobalDeleteSymbolicLink
0x14000c0dc  mov     ebx, 0C000009Ah
0x14000c0e1  xor     edx, edx; Tag
0x14000c0e3  mov     rcx, r12; P
0x14000c0e6  call    cs:__imp_ExFreePoolWithTag
0x14000c0ed  nop     dword ptr [rax+rax+00h]
0x14000c0f2  jmp     loc_14000C2B7
0x14000c0f7  movzx   r8d, [rbp+Src.Length]; Size
0x14000c0fc  mov     rcx, rax; void *
0x14000c0ff  mov     rdx, [rbp+Src.Buffer]; Src
0x14000c103  call    memmove
0x14000c108  movzx   r8d, word ptr [r13+0]
0x14000c10d  xor     eax, eax
0x14000c10f  mov     rdx, [rdi+20h]
0x14000c113  shr     r8, 1
0x14000c116  mov     [rdx+r8*2], ax
0x14000c11b  lea     rax, [r15+10h]
0x14000c11f  mov     byte ptr [rdi+10h], 1
0x14000c123  mov     rdx, [rax+8]
0x14000c127  cmp     [rdx], rax
0x14000c12a  jz      short loc_14000C133
0x14000c12c  mov     ecx, 3
0x14000c131  int     29h; Win8: RtlFailFast(ecx)
0x14000c133  mov     [rdi], rax
0x14000c136  mov     [rdi+8], rdx
0x14000c13a  mov     [rdx], rdi
0x14000c13d  mov     [rax+8], rdi
0x14000c141  mov     rcx, [rsi+170h]
0x14000c148  call    cs:__imp_PsIsHostSilo
0x14000c14f  nop     dword ptr [rax+rax+00h]
0x14000c154  test    al, al
0x14000c156  jz      short loc_14000C160
0x14000c158  mov     rdx, r13
0x14000c15b  call    SendLinkCreated
0x14000c160  lea     rcx, [rbp+Src]; String2
0x14000c164  call    IsDriveLetter
0x14000c169  xor     r13d, r13d
0x14000c16c  test    al, al
0x14000c16e  jz      short loc_14000C18D
0x14000c170  mov     rcx, r14
0x14000c173  call    DeleteNoDriveLetterEntry
0x14000c178  cmp     [r15+85h], r13b
0x14000c17f  jnz     short loc_14000C18D
0x14000c181  lea     rdx, [r15+40h]
0x14000c185  mov     rcx, rsi
0x14000c188  call    PostOnlineNotification
0x14000c18d  movzx   r8d, [rbp+Src.Length]
0x14000c192  mov     dx, 5Ch ; '\'
0x14000c196  mov     rax, [rbp+Src.Buffer]
0x14000c19a  cmp     r8w, 60h ; '`'
0x14000c19f  jz      short loc_14000C1B6
0x14000c1a1  cmp     r8w, 62h ; 'b'
0x14000c1a6  jnz     loc_14000C286
0x14000c1ac  cmp     [rax+60h], dx
0x14000c1b0  jnz     loc_14000C286
0x14000c1b6  cmp     [rax], dx
0x14000c1b9  jnz     loc_14000C286
0x14000c1bf  movzx   ecx, word ptr [rax+2]
0x14000c1c3  cmp     cx, 3Fh ; '?'
0x14000c1c7  jz      short loc_14000C1D2
0x14000c1c9  cmp     cx, dx
0x14000c1cc  jnz     loc_14000C286
0x14000c1d2  cmp     word ptr [rax+4], 3Fh ; '?'
0x14000c1d7  jnz     loc_14000C286
0x14000c1dd  cmp     [rax+6], dx
0x14000c1e1  jnz     loc_14000C286
0x14000c1e7  cmp     word ptr [rax+8], 56h ; 'V'
0x14000c1ec  jnz     loc_14000C286
0x14000c1f2  mov     edx, 6Fh ; 'o'
0x14000c1f7  cmp     [rax+0Ah], dx
0x14000c1fb  jnz     loc_14000C286
0x14000c201  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x14000c206  jnz     short loc_14000C286
0x14000c208  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x14000c20d  jnz     short loc_14000C286
0x14000c20f  mov     edx, 6Dh ; 'm'
0x14000c214  cmp     [rax+10h], dx
0x14000c218  jnz     short loc_14000C286
0x14000c21a  cmp     word ptr [rax+12h], 65h ; 'e'
0x14000c21f  jnz     short loc_14000C286
0x14000c221  cmp     word ptr [rax+14h], 7Bh ; '{'
0x14000c226  jnz     short loc_14000C286
0x14000c228  mov     dx, 2Dh ; '-'
0x14000c22c  cmp     [rax+26h], dx
0x14000c230  jnz     short loc_14000C286
0x14000c232  cmp     [rax+30h], dx
0x14000c236  jnz     short loc_14000C286
0x14000c238  cmp     [rax+3Ah], dx
0x14000c23c  jnz     short loc_14000C286
0x14000c23e  cmp     [rax+44h], dx
0x14000c242  jnz     short loc_14000C286
0x14000c244  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x14000c249  jnz     short loc_14000C286
0x14000c24b  cmp     r8w, 60h ; '`'
0x14000c250  jnz     short loc_14000C286
0x14000c252  cmp     cx, 3Fh ; '?'
0x14000c256  jnz     short loc_14000C286
0x14000c258  cmp     [rsi+90h], r13b
0x14000c25f  jz      short loc_14000C286
0x14000c261  lea     r14, [rsi+10h]
0x14000c265  mov     rdi, [r14]
0x14000c268  jmp     short loc_14000C281
0x14000c26a  cmp     [rdi+84h], r13b
0x14000c271  jz      short loc_14000C27E
0x14000c273  mov     rdx, rdi
0x14000c276  mov     rcx, rsi; Context
0x14000c279  call    ReconcileThisDatabaseWithMaster
0x14000c27e  mov     rdi, [rdi]
0x14000c281  cmp     rdi, r14
0x14000c284  jnz     short loc_14000C26A
0x14000c286  xor     edx, edx; Tag
0x14000c288  mov     rcx, r12; P
0x14000c28b  call    cs:__imp_ExFreePoolWithTag
0x14000c292  nop     dword ptr [rax+rax+00h]
0x14000c297  mov     rcx, rsi
0x14000c29a  call    MountMgrNotify
0x14000c29f  cmp     [r15+81h], r13b
0x14000c2a6  jnz     short loc_14000C2B7
0x14000c2a8  xor     r8d, r8d
0x14000c2ab  lea     rdx, [r15+50h]
0x14000c2af  mov     rcx, rsi
0x14000c2b2  call    MountMgrNotifyNameChange
0x14000c2b7  mov     eax, ebx
0x14000c2b9  add     rsp, 48h
0x14000c2bd  pop     r15
0x14000c2bf  pop     r14
0x14000c2c1  pop     r13
0x14000c2c3  pop     r12
0x14000c2c5  pop     rdi
0x14000c2c6  pop     rsi
0x14000c2c7  pop     rbx
0x14000c2c8  pop     rbp
0x14000c2c9  retn
  ... truncated ...
```
