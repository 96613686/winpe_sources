# SmbShellGetConnectionInfo

- ea: `0x14001fee0`
- end: `0x14002037d`
- name: `SmbShellGetConnectionInfo`
- size: `1181`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001f0e0`

## callees

- `0x140010f94`
- `0x14001fee0`
- `0x14003838c`
- `0x1400383d0`
- `0x140059ea0`
- `0x14007e164`
- `0x14007e1e8`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002024e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002024e`
- `ntoskrnl!ProbeForWrite` at `0x14001ffd4`
- `ntoskrnl!ProbeForWrite` at `0x14001ffed`
- `ntoskrnl!ProbeForWrite` at `0x14001ffd4`
- `ntoskrnl!ProbeForWrite` at `0x14001ffed`
- `ntoskrnl!IoIs32bitProcess` at `0x1400200c3`
- `ntoskrnl!IoIs32bitProcess` at `0x1400200c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002035e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a868`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002035e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a868`
- `rdbss!RxMapUserBuffer` at `0x14001ff92`
- `rdbss!RxMapUserBuffer` at `0x14001ff92`

## pseudocode

```c
__int64 __fastcall SmbShellGetConnectionInfo(PRX_CONTEXT RxContext, __int64 a2)
{
  int v3; // ebx
  KPROCESSOR_MODE RequestorMode; // r14
  unsigned int *v5; // r15
  wchar_t *Buffer; // rsi
  SIZE_T v7; // r12
  PVOID v8; // r13
  unsigned int v9; // ebx
  char v10; // r12
  unsigned int ULongFromUser; // eax
  unsigned int v12; // esi
  unsigned int *v13; // rcx
  unsigned int v15; // [rsp+58h] [rbp-50h] BYREF
  int v16; // [rsp+5Ch] [rbp-4Ch]
  PVOID v17; // [rsp+60h] [rbp-48h] BYREF
  __int64 v18; // [rsp+68h] [rbp-40h]
  bool v20; // [rsp+C0h] [rbp+18h]
  SIZE_T Length; // [rsp+C8h] [rbp+20h] BYREF

  v3 = (__int64)RxContext->RdbssDbgExtension & 0x200;
  RequestorMode = RxContext->CurrentIrp->RequestorMode;
  v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 32LL) + 32LL);
  v5 = (unsigned int *)*((_QWORD *)&RxContext->9 + 19);
  Buffer = RxContext->Create.TransportName.Buffer;
  LODWORD(Length) = *((_DWORD *)&RxContext->9 + 43);
  v7 = *((unsigned int *)&RxContext->9 + 42);
  v17 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_a378b67053473c077e88bb075e0102ae_Traceguids, RxContext);
  }
  v8 = RxMapUserBuffer(RxContext, RxContext->CurrentIrp);
  v16 = (_DWORD)v8 - (_DWORD)Buffer;
  v17 = v8;
  v20 = RxContext->CurrentIrp->MdlAddress != 0;
  if ( !v3 && RequestorMode )
  {
    ProbeForWrite(v5, v7, 1u);
    ProbeForWrite(v8, (unsigned int)Length, 1u);
  }
  if ( !*(_QWORD *)(a2 + 32) )
  {
    v9 = -2147483611;
    v10 = 0;
    goto LABEL_66;
  }
  if ( (unsigned int)v7 < 0x24 )
  {
    v9 = -1073741789;
    v10 = 0;
    goto LABEL_66;
  }
  if ( RequestorMode )
    ULongFromUser = RtlReadULongFromUser(v5 + 1);
  else
    ULongFromUser = v5[1];
  if ( ULongFromUser != 6 )
  {
    v9 = -1073741811;
    v10 = 0;
    goto LABEL_66;
  }
  if ( RequestorMode )
    v12 = RtlReadULongFromUser(v5 + 2);
  else
    v12 = v5[2];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_a378b67053473c077e88bb075e0102ae_Traceguids, v12);
  }
  if ( IoIs32bitProcess(RxContext->CurrentIrp) )
  {
    if ( v12 )
    {
      switch ( v12 )
      {
        case 1u:
          if ( (unsigned int)Length < 0x18 )
          {
            v9 = -1073741789;
            v10 = 0;
            goto LABEL_66;
          }
          break;
        case 2u:
          if ( (unsigned int)Length < 0x44 )
          {
            v9 = -1073741789;
            v10 = 0;
            goto LABEL_66;
          }
          break;
        case 3u:
          if ( (unsigned int)Length < 0xD0 )
          {
            v9 = -1073741789;
            v10 = 0;
            goto LABEL_66;
          }
          break;
        default:
          v9 = -1073741821;
          v10 = 0;
          goto LABEL_66;
      }
    }
    else if ( (unsigned int)Length < 0xC )
    {
      v9 = -1073741789;
      v10 = 0;
      goto LABEL_66;
    }
  }
  else if ( v12 )
  {
    switch ( v12 )
    {
      case 1u:
        if ( (unsigned int)Length < 0x20 )
        {
          v9 = -1073741789;
          v10 = 0;
          goto LABEL_66;
        }
        break;
      case 2u:
        if ( (unsigned int)Length < 0x60 )
        {
          v9 = -1073741789;
          v10 = 0;
          goto LABEL_66;
        }
        break;
      case 3u:
        if ( (unsigned int)Length < 0xF0 )
        {
          v9 = -1073741789;
          v10 = 0;
          goto LABEL_66;
        }
        break;
      default:
        v9 = -1073741821;
        v10 = 0;
        goto LABEL_66;
    }
  }
  else if ( (unsigned int)Length < 0x18 )
  {
    v9 = -1073741789;
    v10 = 0;
    goto LABEL_66;
  }
  if ( RequestorMode )
    RtlWriteULongToUser(v5 + 6, 1);
  else
    v5[6] = 1;
  ExAcquireResourceExclusiveLite(
    (PERESOURCE)&RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink[1].Blink,
    1u);
  v10 = 1;
  if ( !(*(unsigned int (__fastcall **)(PRX_CONTEXT, __int64, _QWORD, PVOID *, SIZE_T *, int, unsigned int *, bool))(*(_QWORD *)(v18 + 56) + 792LL))(
          RxContext,
          a2,
          v12,
          &v17,
          &Length,
          v16,
          &v15,
          v20) )
  {
    if ( RequestorMode )
      RtlWriteULongToUser(v5 + 5, 1);
    else
      v5[5] = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_a378b67053473c077e88bb075e0102ae_Traceguids, v8);
    }
  }
  v13 = v5 + 7;
  if ( RequestorMode )
    RtlWriteULongToUser(v13, v15);
  else
    *v13 = v15;
  RxContext->InformationToReturn = v15;
  v9 = 0;
LABEL_66:
  if ( v10 )
    ExReleaseResourceLite((PERESOURCE)&RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink[1].Blink);
  return v9;
}

```

## disassembly

```asm
0x14001fee0  mov     r11, rsp
0x14001fee3  mov     [r11+10h], rdx
0x14001fee7  mov     [r11+8], rcx
0x14001feeb  push    rbx
0x14001feec  push    rsi
0x14001feed  push    rdi
0x14001feee  push    r12
0x14001fef0  push    r13
0x14001fef2  push    r14
0x14001fef4  push    r15
0x14001fef6  sub     rsp, 70h
0x14001fefa  mov     rdi, rcx
0x14001fefd  mov     ebx, [rcx+78h]
0x14001ff00  and     ebx, 200h
0x14001ff06  mov     rax, [rcx+28h]
0x14001ff0a  mov     r14b, [rax+40h]
0x14001ff0e  mov     rax, [rdx+20h]
0x14001ff12  mov     rdx, [rax+20h]
0x14001ff16  mov     rax, [rdx+20h]
0x14001ff1a  mov     [rsp+0A8h+var_40], rax
0x14001ff1f  mov     r15, [rcx+228h]
0x14001ff26  mov     rsi, [rcx+230h]
0x14001ff2d  mov     eax, [rcx+23Ch]
0x14001ff33  mov     [r11+20h], eax
0x14001ff37  mov     r12d, [rcx+238h]
0x14001ff3e  mov     qword ptr [r11-48h], 0
0x14001ff46  mov     [rsp+0A8h+var_58], 0
0x14001ff4b  mov     [rsp+0A8h+var_50], 0
0x14001ff53  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ff5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ff61  cmp     rcx, rax
0x14001ff64  jz      short loc_14001FF8B
0x14001ff66  mov     eax, [rcx+2Ch]
0x14001ff69  test    al, 2
0x14001ff6b  jz      short loc_14001FF8B
0x14001ff6d  cmp     byte ptr [rcx+29h], 4
0x14001ff71  jb      short loc_14001FF8B
0x14001ff73  mov     edx, 0Fh
0x14001ff78  mov     r9, rdi
0x14001ff7b  lea     r8, WPP_a378b67053473c077e88bb075e0102ae_Traceguids
0x14001ff82  mov     rcx, [rcx+18h]
0x14001ff86  call    WPP_SF_q
0x14001ff8b  mov     rdx, [rdi+28h]; Irp
0x14001ff8f  mov     rcx, rdi; RxContext
0x14001ff92  call    cs:__imp_RxMapUserBuffer
0x14001ff99  nop     dword ptr [rax+rax+00h]
0x14001ff9e  mov     r13, rax
0x14001ffa1  sub     eax, esi
0x14001ffa3  mov     [rsp+0A8h+var_4C], eax
0x14001ffa7  mov     [rsp+0A8h+var_48], r13
0x14001ffac  mov     rcx, [rdi+28h]
0x14001ffb0  cmp     qword ptr [rcx+8], 0
0x14001ffb5  setnz   [rsp+0A8h+arg_10]
0x14001ffbd  test    ebx, ebx
0x14001ffbf  jnz     short loc_140020005
0x14001ffc1  test    r14b, r14b
0x14001ffc4  jz      short loc_140020005
0x14001ffc6  mov     rdx, r12; Length
0x14001ffc9  mov     ebx, 1
0x14001ffce  mov     r8d, ebx; Alignment
0x14001ffd1  mov     rcx, r15; Address
0x14001ffd4  call    cs:__imp_ProbeForWrite
0x14001ffdb  nop     dword ptr [rax+rax+00h]
0x14001ffe0  mov     edx, dword ptr [rsp+0A8h+Length]; Length
0x14001ffe7  mov     r8d, ebx; Alignment
0x14001ffea  mov     rcx, r13; Address
0x14001ffed  call    cs:__imp_ProbeForWrite
0x14001fff4  nop     dword ptr [rax+rax+00h]
0x14001fff9  jmp     short loc_14002000A
0x14001fffb  mov     eax, 0C000000Dh
0x140020000  jmp     loc_14002036C
0x140020005  mov     ebx, 1
0x14002000a  mov     rax, [rsp+0A8h+arg_8]
0x140020012  cmp     qword ptr [rax+20h], 0
0x140020017  jnz     short loc_14002002C
0x140020019  mov     ebx, 80000025h
0x14002001e  mov     [rsp+0A8h+var_54], ebx
0x140020022  mov     r12b, [rsp+0A8h+var_58]
0x140020027  jmp     loc_14002034A
0x14002002c  cmp     r12d, 24h ; '$'
0x140020030  jnb     short loc_140020045
0x140020032  mov     ebx, 0C0000023h
0x140020037  mov     [rsp+0A8h+var_54], ebx
0x14002003b  mov     r12b, [rsp+0A8h+var_58]
0x140020040  jmp     loc_14002034A
0x140020045  test    r14b, r14b
0x140020048  jz      short loc_140020055
0x14002004a  lea     rcx, [r15+4]
0x14002004e  call    RtlReadULongFromUser
0x140020053  jmp     short loc_140020059
0x140020055  mov     eax, [r15+4]
0x140020059  cmp     eax, 6
0x14002005c  jz      short loc_140020071
0x14002005e  mov     ebx, 0C000000Dh
0x140020063  mov     [rsp+0A8h+var_54], ebx
0x140020067  mov     r12b, [rsp+0A8h+var_58]
0x14002006c  jmp     loc_14002034A
0x140020071  test    r14b, r14b
0x140020074  jz      short loc_140020083
0x140020076  lea     rcx, [r15+8]
0x14002007a  call    RtlReadULongFromUser
0x14002007f  mov     esi, eax
0x140020081  jmp     short loc_140020087
0x140020083  mov     esi, [r15+8]
0x140020087  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002008e  lea     rax, WPP_GLOBAL_Control
0x140020095  cmp     rcx, rax
0x140020098  jz      short loc_1400200BF
0x14002009a  mov     eax, [rcx+2Ch]
0x14002009d  test    al, 2
0x14002009f  jz      short loc_1400200BF
0x1400200a1  cmp     byte ptr [rcx+29h], 4
0x1400200a5  jb      short loc_1400200BF
0x1400200a7  mov     edx, 10h
0x1400200ac  mov     r9d, esi
0x1400200af  lea     r8, WPP_a378b67053473c077e88bb075e0102ae_Traceguids
0x1400200b6  mov     rcx, [rcx+18h]
0x1400200ba  call    WPP_SF_d
0x1400200bf  mov     rcx, [rdi+28h]; Irp
0x1400200c3  call    cs:__imp_IoIs32bitProcess
0x1400200ca  nop     dword ptr [rax+rax+00h]
0x1400200cf  test    al, al
0x1400200d1  mov     eax, esi
0x1400200d3  jz      loc_14002018A
0x1400200d9  test    esi, esi
0x1400200db  jz      loc_140020169
0x1400200e1  sub     eax, 1
0x1400200e4  jz      short loc_140020148
0x1400200e6  sub     eax, 1
0x1400200e9  jz      short loc_140020127
0x1400200eb  sub     eax, 1
0x1400200ee  jz      short loc_140020103
0x1400200f0  mov     ebx, 0C0000003h
0x1400200f5  mov     [rsp+0A8h+var_54], ebx
0x1400200f9  mov     r12b, [rsp+0A8h+var_58]
0x1400200fe  jmp     loc_14002034A
0x140020103  cmp     dword ptr [rsp+0A8h+Length], 0D0h
0x14002010e  jnb     loc_140020227
0x140020114  mov     ebx, 0C0000023h
0x140020119  mov     [rsp+0A8h+var_54], ebx
0x14002011d  mov     r12b, [rsp+0A8h+var_58]
0x140020122  jmp     loc_14002034A
0x140020127  cmp     dword ptr [rsp+0A8h+Length], 44h ; 'D'
0x14002012f  jnb     loc_140020227
0x140020135  mov     ebx, 0C0000023h
0x14002013a  mov     [rsp+0A8h+var_54], ebx
0x14002013e  mov     r12b, [rsp+0A8h+var_58]
0x140020143  jmp     loc_14002034A
0x140020148  cmp     dword ptr [rsp+0A8h+Length], 18h
0x140020150  jnb     loc_140020227
0x140020156  mov     ebx, 0C0000023h
0x14002015b  mov     [rsp+0A8h+var_54], ebx
0x14002015f  mov     r12b, [rsp+0A8h+var_58]
0x140020164  jmp     loc_14002034A
0x140020169  cmp     dword ptr [rsp+0A8h+Length], 0Ch
0x140020171  jnb     loc_140020227
0x140020177  mov     ebx, 0C0000023h
0x14002017c  mov     [rsp+0A8h+var_54], ebx
0x140020180  mov     r12b, [rsp+0A8h+var_58]
0x140020185  jmp     loc_14002034A
0x14002018a  test    esi, esi
0x14002018c  jz      short loc_14002020A
0x14002018e  sub     eax, 1
0x140020191  jz      short loc_1400201ED
0x140020193  sub     eax, 1
0x140020196  jz      short loc_1400201D0
0x140020198  sub     eax, 1
0x14002019b  jz      short loc_1400201B0
0x14002019d  mov     ebx, 0C0000003h
0x1400201a2  mov     [rsp+0A8h+var_54], ebx
0x1400201a6  mov     r12b, [rsp+0A8h+var_58]
0x1400201ab  jmp     loc_14002034A
0x1400201b0  cmp     dword ptr [rsp+0A8h+Length], 0F0h
0x1400201bb  jnb     short loc_140020227
0x1400201bd  mov     ebx, 0C0000023h
0x1400201c2  mov     [rsp+0A8h+var_54], ebx
0x1400201c6  mov     r12b, [rsp+0A8h+var_58]
0x1400201cb  jmp     loc_14002034A
0x1400201d0  cmp     dword ptr [rsp+0A8h+Length], 60h ; '`'
0x1400201d8  jnb     short loc_140020227
0x1400201da  mov     ebx, 0C0000023h
0x1400201df  mov     [rsp+0A8h+var_54], ebx
0x1400201e3  mov     r12b, [rsp+0A8h+var_58]
0x1400201e8  jmp     loc_14002034A
0x1400201ed  cmp     dword ptr [rsp+0A8h+Length], 20h ; ' '
0x1400201f5  jnb     short loc_140020227
0x1400201f7  mov     ebx, 0C0000023h
0x1400201fc  mov     [rsp+0A8h+var_54], ebx
0x140020200  mov     r12b, [rsp+0A8h+var_58]
0x140020205  jmp     loc_14002034A
0x14002020a  cmp     dword ptr [rsp+0A8h+Length], 18h
0x140020212  jnb     short loc_140020227
0x140020214  mov     ebx, 0C0000023h
0x140020219  mov     [rsp+0A8h+var_54], ebx
0x14002021d  mov     r12b, [rsp+0A8h+var_58]
0x140020222  jmp     loc_14002034A
0x140020227  test    r14b, r14b
0x14002022a  jz      short loc_140020239
0x14002022c  mov     edx, ebx
0x14002022e  lea     rcx, [r15+18h]
0x140020232  call    RtlWriteULongToUser
0x140020237  jmp     short loc_14002023D
0x140020239  mov     [r15+18h], ebx
0x14002023d  mov     rax, [rdi+50h]
0x140020241  mov     rcx, [rax+1F8h]
0x140020248  add     rcx, 18h; Resource
0x14002024c  mov     dl, bl; Wait
0x14002024e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140020255  nop     dword ptr [rax+rax+00h]
0x14002025a  mov     r12b, bl
0x14002025d  mov     [rsp+0A8h+var_58], bl
0x140020261  mov     rax, [rsp+0A8h+var_40]
0x140020266  mov     rax, [rax+38h]
0x14002026a  mov     rax, [rax+318h]
0x140020271  mov     cl, [rsp+0A8h+arg_10]
0x140020278  mov     [rsp+0A8h+var_70], cl
0x14002027c  lea     rcx, [rsp+0A8h+var_50]
0x140020281  mov     [rsp+0A8h+var_78], rcx
0x140020286  mov     ecx, [rsp+0A8h+var_4C]
0x14002028a  mov     [rsp+0A8h+var_80], ecx
0x14002028e  lea     rcx, [rsp+0A8h+Length]
0x140020296  mov     [rsp+0A8h+var_88], rcx
0x14002029b  lea     r9, [rsp+0A8h+var_48]
0x1400202a0  mov     r8d, esi
0x1400202a3  mov     rdx, [rsp+0A8h+arg_8]
0x1400202ab  mov     rcx, rdi
0x1400202ae  call    _guard_dispatch_icall
0x1400202b3  mov     [rsp+0A8h+var_54], eax
0x1400202b7  test    eax, eax
0x1400202b9  jnz     short loc_140020309
0x1400202bb  test    r14b, r14b
0x1400202be  jz      short loc_1400202CD
0x1400202c0  mov     edx, ebx
0x1400202c2  lea     rcx, [r15+14h]
0x1400202c6  call    RtlWriteULongToUser
0x1400202cb  jmp     short loc_1400202D1
0x1400202cd  mov     [r15+14h], ebx
0x1400202d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400202d8  lea     rax, WPP_GLOBAL_Control
0x1400202df  cmp     rcx, rax
0x1400202e2  jz      short loc_140020309
0x1400202e4  mov     eax, [rcx+2Ch]
0x1400202e7  test    al, 2
0x1400202e9  jz      short loc_140020309
0x1400202eb  cmp     byte ptr [rcx+29h], 4
0x1400202ef  jb      short loc_140020309
0x1400202f1  mov     edx, 11h
0x1400202f6  mov     r9, r13
0x1400202f9  lea     r8, WPP_a378b67053473c077e88bb075e0102ae_Traceguids
0x140020300  mov     rcx, [rcx+18h]
0x140020304  call    WPP_SF_Z
0x140020309  mov     eax, [rsp+0A8h+var_50]
0x14002030d  lea     rcx, [r15+1Ch]
0x140020311  test    r14b, r14b
0x140020314  jz      short loc_14002031F
0x140020316  mov     edx, eax
0x140020318  call    RtlWriteULongToUser
0x14002031d  jmp     short loc_140020321
0x14002031f  mov     [rcx], eax
0x140020321  mov     eax, [rsp+0A8h+var_50]
0x140020325  mov     [rdi+0B8h], rax
0x14002032c  xor     ebx, ebx
0x14002032e  mov     [rsp+0A8h+var_54], ebx
0x140020332  jmp     short loc_14002034A
0x140020334  mov     ebx, 0C000000Dh
0x140020339  mov     [rsp+0A8h+var_54], ebx
0x14002033d  mov     rdi, [rsp+0A8h+arg_0]
0x140020345  mov     r12b, [rsp+0A8h+var_58]
0x14002034a  test    r12b, r12b
0x14002034d  jz      short loc_14002036A
0x14002034f  mov     rcx, [rdi+50h]
0x140020353  mov     rcx, [rcx+1F8h]
0x14002035a  add     rcx, 18h; Resource
0x14002035e  call    cs:__imp_ExReleaseResourceLite
0x140020365  nop     dword ptr [rax+rax+00h]
0x14002036a  mov     eax, ebx
0x14002036c  add     rsp, 70h
0x140020370  pop     r15
0x140020372  pop     r14
0x140020374  pop     r13
0x140020376  pop     r12
0x140020378  pop     rdi
0x140020379  pop     rsi
0x14002037a  pop     rbx
0x14002037b  retn
0x14005a843  push    rbp
0x14005a845  sub     rsp, 50h
0x14005a849  mov     rbp, rdx
0x14005a84c  cmp     byte ptr [rbp+50h], 0
0x14005a850  jz      short loc_14005A875
0x14005a852  mov     rax, [rbp+0B0h]
0x14005a859  mov     rcx, [rax+50h]
0x14005a85d  mov     rcx, [rcx+1F8h]
0x14005a864  add     rcx, 18h; Resource
0x14005a868  call    cs:__imp_ExReleaseResourceLite
0x14005a86f  nop     dword ptr [rax+rax+00h]
0x14005a874  nop
0x14005a875  add     rsp, 50h
0x14005a879  pop     rbp
0x14005a87a  retn
  ... truncated ...
```
