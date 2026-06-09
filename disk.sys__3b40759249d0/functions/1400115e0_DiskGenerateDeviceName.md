# DiskGenerateDeviceName

- ea: `0x1400115e0`
- end: `0x140011812`
- name: `DiskGenerateDeviceName`
- size: `562`
- prototype: `__int64 __fastcall(int, PVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140015350`

## callees

- `0x1400040a8`
- `0x140004370`
- `0x1400057ac`
- `0x140005bf0`
- `0x140006000`
- `0x1400115e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400117de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117de`
- `ntoskrnl!ExAllocatePool2` at `0x1400116b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400116b2`

## pseudocode

```c
__int64 __fastcall DiskGenerateDeviceName(int a1, PVOID *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rdx
  _BYTE *Pool2; // rax
  _BYTE *v9; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  char *v13; // r8
  _BYTE *v14; // rax
  int v15; // [rsp+20h] [rbp-68h]
  char pszDest[64]; // [rsp+30h] [rbp-58h] BYREF

  memset(pszDest, 0, sizeof(pszDest));
  v15 = diskDeviceSequenceNumber++;
  v4 = RtlStringCchPrintfA(pszDest, 0x3Fu, "\\Device\\Harddisk%d\\DR%d", a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids,
        (unsigned int)v4);
    }
    return v5;
  }
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( pszDest[v7] );
  Pool2 = (_BYTE *)ExAllocatePool2(256, v7 + 1, 1313104723);
  *a2 = Pool2;
  v9 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  do
    ++v6;
  while ( pszDest[v6] );
  v11 = v6 + 1;
  if ( v6 == -1 )
  {
    v5 = -1073741811;
    if ( !v11 )
      goto LABEL_28;
    goto LABEL_27;
  }
  if ( v11 > 0x7FFFFFFF )
  {
    v5 = -1073741811;
LABEL_27:
    *Pool2 = 0;
LABEL_28:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids, v5);
    }
    if ( *a2 )
    {
      ExFreePoolWithTag(*a2, 0);
      *a2 = 0;
    }
    return v5;
  }
  v12 = 2147483646;
  v13 = pszDest;
  do
  {
    if ( !v12 )
      break;
    if ( !*v13 )
      break;
    *v9++ = *v13++;
    --v12;
    --v11;
  }
  while ( v11 );
  v14 = v9 - 1;
  if ( v11 )
    v14 = v9;
  *v14 = 0;
  v5 = v11 == 0 ? 0x80000005 : 0;
  if ( !v11 )
    goto LABEL_28;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids, pszDest);
  }
  return 0;
}

```

## disassembly

```asm
0x1400115e0  mov     [rsp+arg_10], rbx
0x1400115e5  push    rdi
0x1400115e6  sub     rsp, 80h
0x1400115ed  mov     rax, cs:__security_cookie
0x1400115f4  xor     rax, rsp
0x1400115f7  mov     [rsp+88h+var_18], rax
0x1400115fc  mov     rdi, rdx
0x1400115ff  mov     ebx, ecx
0x140011601  xor     edx, edx; Val
0x140011603  lea     rcx, [rsp+88h+pszDest]; void *
0x140011608  lea     r8d, [rdx+40h]; Size
0x14001160c  call    memset
0x140011611  mov     ecx, cs:diskDeviceSequenceNumber
0x140011617  lea     r8, aDeviceHarddisk_0; "\\Device\\Harddisk%d\\DR%d"
0x14001161e  mov     [rsp+88h+var_68], ecx
0x140011622  mov     r9d, ebx
0x140011625  mov     edx, 3Fh ; '?'; cchDest
0x14001162a  lea     eax, [rcx+1]
0x14001162d  lea     rcx, [rsp+88h+pszDest]; pszDest
0x140011632  mov     cs:diskDeviceSequenceNumber, eax
0x140011638  call    RtlStringCchPrintfA
0x14001163d  mov     ebx, eax
0x14001163f  test    eax, eax
0x140011641  jns     short loc_14001168F
0x140011643  mov     r10, cs:WPP_GLOBAL_Control
0x14001164a  lea     rcx, WPP_GLOBAL_Control
0x140011651  cmp     r10, rcx
0x140011654  jz      loc_1400117F1
0x14001165a  mov     edx, [r10+2Ch]
0x14001165e  test    dl, 2
0x140011661  jz      loc_1400117F1
0x140011667  cmp     byte ptr [r10+29h], 2
0x14001166c  jb      loc_1400117F1
0x140011672  mov     rcx, [r10+18h]
0x140011676  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x14001167d  mov     edx, 0Fh
0x140011682  mov     r9d, eax
0x140011685  call    WPP_SF_D
0x14001168a  jmp     loc_1400117F1
0x14001168f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140011693  lea     rax, [rsp+88h+pszDest]
0x140011698  mov     rdx, rbx
0x14001169b  inc     rdx
0x14001169e  cmp     byte ptr [rax+rdx], 0
0x1400116a2  jnz     short loc_14001169B
0x1400116a4  inc     rdx
0x1400116a7  mov     ecx, 100h
0x1400116ac  mov     r8d, 4E446353h
0x1400116b2  call    cs:__imp_ExAllocatePool2
0x1400116b9  nop     dword ptr [rax+rax+00h]
0x1400116be  mov     [rdi], rax
0x1400116c1  mov     rdx, rax
0x1400116c4  test    rax, rax
0x1400116c7  jnz     short loc_1400116D3
0x1400116c9  mov     eax, 0C000009Ah
0x1400116ce  jmp     loc_1400117F3
0x1400116d3  lea     rax, [rsp+88h+pszDest]
0x1400116d8  inc     rbx
0x1400116db  cmp     byte ptr [rax+rbx], 0
0x1400116df  jnz     short loc_1400116D8
0x1400116e1  lea     rcx, [rbx+1]
0x1400116e5  test    rcx, rcx
0x1400116e8  jz      loc_14001178D
0x1400116ee  cmp     rcx, 7FFFFFFFh
0x1400116f5  jbe     short loc_140011701
0x1400116f7  mov     ebx, 0C000000Dh
0x1400116fc  jmp     loc_140011797
0x140011701  mov     eax, 7FFFFFFEh
0x140011706  lea     r8, [rsp+88h+pszDest]
0x14001170b  test    rax, rax
0x14001170e  jz      short loc_14001172A
0x140011710  mov     r9b, [r8]
0x140011713  test    r9b, r9b
0x140011716  jz      short loc_14001172A
0x140011718  mov     [rdx], r9b
0x14001171b  inc     r8
0x14001171e  inc     rdx
0x140011721  dec     rax
0x140011724  sub     rcx, 1
0x140011728  jnz     short loc_14001170B
0x14001172a  test    rcx, rcx
0x14001172d  lea     rax, [rdx-1]
0x140011731  cmovnz  rax, rdx
0x140011735  mov     byte ptr [rax], 0
0x140011738  mov     rax, rcx
0x14001173b  neg     rax
0x14001173e  sbb     ebx, ebx
0x140011740  not     ebx
0x140011742  and     ebx, 80000005h
0x140011748  test    rcx, rcx
0x14001174b  jz      short loc_14001179A
0x14001174d  mov     r10, cs:WPP_GLOBAL_Control
0x140011754  lea     rcx, WPP_GLOBAL_Control
0x14001175b  cmp     r10, rcx
0x14001175e  jz      short loc_140011789
0x140011760  mov     eax, [r10+2Ch]
0x140011764  test    al, 2
0x140011766  jz      short loc_140011789
0x140011768  cmp     byte ptr [r10+29h], 4
0x14001176d  jb      short loc_140011789
0x14001176f  mov     rcx, [r10+18h]
0x140011773  lea     r9, [rsp+88h+pszDest]
0x140011778  mov     edx, 11h
0x14001177d  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x140011784  call    WPP_SF_s
0x140011789  xor     eax, eax
0x14001178b  jmp     short loc_1400117F3
0x14001178d  mov     ebx, 0C000000Dh
0x140011792  test    rcx, rcx
0x140011795  jz      short loc_14001179A
0x140011797  mov     byte ptr [rdx], 0
0x14001179a  mov     r10, cs:WPP_GLOBAL_Control
0x1400117a1  lea     rcx, WPP_GLOBAL_Control
0x1400117a8  cmp     r10, rcx
0x1400117ab  jz      short loc_1400117D4
0x1400117ad  mov     eax, [r10+2Ch]
0x1400117b1  test    al, 2
0x1400117b3  jz      short loc_1400117D4
0x1400117b5  cmp     byte ptr [r10+29h], 2
0x1400117ba  jb      short loc_1400117D4
0x1400117bc  mov     rcx, [r10+18h]
0x1400117c0  lea     r8, WPP_05abe5c235553bdb89a3b8ecfd575366_Traceguids
0x1400117c7  mov     edx, 10h
0x1400117cc  mov     r9d, ebx
0x1400117cf  call    WPP_SF_D
0x1400117d4  mov     rcx, [rdi]; P
0x1400117d7  test    rcx, rcx
0x1400117da  jz      short loc_1400117F1
0x1400117dc  xor     edx, edx; Tag
0x1400117de  call    cs:__imp_ExFreePoolWithTag
0x1400117e5  nop     dword ptr [rax+rax+00h]
0x1400117ea  mov     qword ptr [rdi], 0
0x1400117f1  mov     eax, ebx
0x1400117f3  mov     rcx, [rsp+88h+var_18]
0x1400117f8  xor     rcx, rsp; StackCookie
0x1400117fb  call    __security_check_cookie
0x140011800  mov     rbx, [rsp+88h+arg_10]
0x140011808  add     rsp, 80h
0x14001180f  pop     rdi
0x140011810  retn
```
