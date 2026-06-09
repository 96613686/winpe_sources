# MdaGetDefaultMountInfo

- ea: `0x140036354`
- end: `0x140036776`
- name: `MdaGetDefaultMountInfo`
- size: `1058`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x140025be0`
- `0x14003677c`

## callees

- `0x14000b680`
- `0x1400159cc`
- `0x1400159fc`
- `0x140034600`
- `0x140036354`

## string_xrefs

- `0x1400363b7`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x1400364b0`: `MountType`
- `0x14003660a`: `DeleteSymlinks`
- `0x140036633`: `DisplayAllLinks`
- `0x1400364f0`: `Access`
- `0x140036591`: `NFSReaddir`
- `0x140036514`: `SymLinks`
- `0x14003665c`: `EUCMount`
- `0x1400363e2`: `ReadBuffer`
- `0x140036413`: `WriteBuffer`
- `0x140036540`: `FileAttributeCache`
- `0x1400365ba`: `RemoteWriteCache`

## pseudocode

```c
__int64 __fastcall MdaGetDefaultMountInfo(_DWORD *a1)
{
  int v2; // edi
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // edi
  int v7; // ecx
  unsigned int v9; // [rsp+70h] [rbp+30h] BYREF

  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
  a1[5] = 8;
  a1[3] = 0x100000;
  a1[4] = 0x100000;
  a1[6] = 5;
  a1[7] = 1;
  v2 = 1024;
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              L"ReadBuffer",
              &v9) >= 0 )
  {
    v3 = v9;
    if ( v9 > 0x400 )
    {
      if ( v9 >= 0x100000 )
        v3 = 0x100000;
    }
    else
    {
      v3 = 1024;
    }
    a1[3] = v3;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              L"WriteBuffer",
              &v9) >= 0 )
  {
    if ( v9 > 0x400 )
    {
      v2 = v9;
      if ( v9 >= 0x100000 )
        v2 = 0x100000;
    }
    a1[4] = v2;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              L"Timeout",
              &v9) >= 0 )
  {
    v4 = v9;
    if ( v9 > 1 )
    {
      if ( v9 >= 0x270F )
        v4 = 9999;
    }
    else
    {
      v4 = 1;
    }
    a1[5] = v4;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              L"Retransmissions",
              &v9) >= 0 )
  {
    v5 = 0;
    if ( v9 )
      v5 = v9;
    if ( v5 >= 0x270F )
      v5 = 9999;
    a1[6] = v5;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
              L"MountType",
              &v9) >= 0 )
    a1[7] = (v9 > 1) + 1;
  a1[8] = 493;
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"Access",
              &v9) >= 0 )
    a1[8] = v9;
  a1[14] |= 0x39Cu;
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"SymLinks",
              &v9) >= 0
    && !v9 )
  {
    a1[14] &= ~0x200u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"FileAttributeCache",
              &v9) >= 0
    && !v9 )
  {
    a1[14] &= ~0x10u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"NFSLookup",
              &v9) >= 0
    && !v9 )
  {
    a1[14] &= ~0x80u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"NFSReaddir",
              &v9) >= 0
    && !v9 )
  {
    a1[14] &= ~0x100u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"RemoteWriteCache",
              &v9) >= 0
    && !v9 )
  {
    a1[14] &= ~8u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"Locking",
              &v9) >= 0
    && v9 )
  {
    a1[14] |= 1u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"DeleteSymlinks",
              &v9) >= 0
    && v9 )
  {
    a1[14] |= 0x1000u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"DisplayAllLinks",
              &v9) >= 0
    && v9 )
  {
    a1[14] |= 0x800u;
  }
  if ( (int)NfsReadUserRegistry(
              &stru_140041090,
              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
              L"EUCMount",
              &v9) >= 0
    && (v9 == 64
     || v9 == 0x2000
     || v9 == 0x4000
     || v9 == 0x8000
     || v9 == 0x10000
     || v9 == 0x20000
     || v9 == 0x40000
     || v9 == 0x80000) )
  {
    a1[14] |= v9;
  }
  v9 = 0;
  v6 = NfsReadUserRegistry(
         &stru_140041090,
         L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
         L"SecFlavors",
         &v9);
  v7 = v9 & 0xF;
  if ( (v9 & 0xF) == 0 )
    v7 = 15;
  a1[15] = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_ddddd(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids,
        (unsigned int)a1[3],
        a1[4],
        a1[5],
        a1[6],
        a1[7]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x140036354  mov     [rsp-28h+arg_8], rbx
0x140036359  mov     [rsp-28h+arg_10], rsi
0x14003635e  push    rbp
0x14003635f  push    rdi
0x140036360  push    r12
0x140036362  push    r14
0x140036364  push    r15
0x140036366  mov     rbp, rsp
0x140036369  sub     rsp, 40h
0x14003636d  xor     esi, esi
0x14003636f  mov     rbx, rcx
0x140036372  mov     [rbp+arg_0], esi
0x140036375  mov     rcx, cs:WPP_GLOBAL_Control
0x14003637c  lea     rax, WPP_GLOBAL_Control
0x140036383  cmp     rcx, rax
0x140036386  jz      short loc_1400363A2
0x140036388  mov     eax, [rcx+2Ch]
0x14003638b  test    al, 8
0x14003638d  jz      short loc_1400363A2
0x14003638f  mov     rcx, [rcx+18h]
0x140036393  lea     edx, [rsi+17h]
0x140036396  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003639d  call    WPP_SF_
0x1400363a2  mov     r15d, 100000h
0x1400363a8  mov     dword ptr [rbx+14h], 8
0x1400363af  lea     rax, [rbp+arg_0]
0x1400363b3  mov     [rbx+0Ch], r15d
0x1400363b7  lea     r12, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1400363be  mov     [rbx+10h], r15d
0x1400363c2  lea     r14, stru_140041090
0x1400363c9  mov     dword ptr [rbx+18h], 5
0x1400363d0  mov     rdx, r12; PCWSTR
0x1400363d3  mov     dword ptr [rbx+1Ch], 1
0x1400363da  mov     rcx, r14; SourceString
0x1400363dd  mov     [rsp+40h+var_20], rax; void *
0x1400363e2  lea     r8, aReadbuffer; "ReadBuffer"
0x1400363e9  call    NfsReadUserRegistry
0x1400363ee  mov     edi, 400h
0x1400363f3  test    eax, eax
0x1400363f5  js      short loc_14003640C
0x1400363f7  mov     eax, [rbp+arg_0]
0x1400363fa  cmp     eax, edi
0x1400363fc  ja      short loc_140036402
0x1400363fe  mov     eax, edi
0x140036400  jmp     short loc_140036409
0x140036402  cmp     eax, r15d
0x140036405  cmovnb  eax, r15d
0x140036409  mov     [rbx+0Ch], eax
0x14003640c  lea     rax, [rbp+arg_0]
0x140036410  mov     rdx, r12; PCWSTR
0x140036413  lea     r8, aWritebuffer; "WriteBuffer"
0x14003641a  mov     [rsp+40h+var_20], rax; void *
0x14003641f  mov     rcx, r14; SourceString
0x140036422  call    NfsReadUserRegistry
0x140036427  test    eax, eax
0x140036429  js      short loc_14003643D
0x14003642b  cmp     [rbp+arg_0], edi
0x14003642e  jbe     short loc_14003643A
0x140036430  mov     edi, [rbp+arg_0]
0x140036433  cmp     edi, r15d
0x140036436  cmovnb  edi, r15d
0x14003643a  mov     [rbx+10h], edi
0x14003643d  lea     rax, [rbp+arg_0]
0x140036441  mov     rdx, r12; PCWSTR
0x140036444  lea     r8, aTimeout; "Timeout"
0x14003644b  mov     [rsp+40h+var_20], rax; void *
0x140036450  mov     rcx, r14; SourceString
0x140036453  call    NfsReadUserRegistry
0x140036458  mov     edi, 270Fh
0x14003645d  test    eax, eax
0x14003645f  js      short loc_140036478
0x140036461  mov     eax, [rbp+arg_0]
0x140036464  cmp     eax, 1
0x140036467  ja      short loc_140036470
0x140036469  mov     eax, 1
0x14003646e  jmp     short loc_140036475
0x140036470  cmp     eax, edi
0x140036472  cmovnb  eax, edi
0x140036475  mov     [rbx+14h], eax
0x140036478  lea     rax, [rbp+arg_0]
0x14003647c  mov     rdx, r12; PCWSTR
0x14003647f  lea     r8, aRetransmission; "Retransmissions"
0x140036486  mov     [rsp+40h+var_20], rax; void *
0x14003648b  mov     rcx, r14; SourceString
0x14003648e  call    NfsReadUserRegistry
0x140036493  test    eax, eax
0x140036495  js      short loc_1400364A9
0x140036497  mov     eax, [rbp+arg_0]
0x14003649a  mov     ecx, esi
0x14003649c  test    eax, eax
0x14003649e  cmovnz  ecx, eax
0x1400364a1  cmp     ecx, edi
0x1400364a3  cmovnb  ecx, edi
0x1400364a6  mov     [rbx+18h], ecx
0x1400364a9  lea     rax, [rbp+arg_0]
0x1400364ad  mov     rdx, r12; PCWSTR
0x1400364b0  lea     r8, aMounttype; "MountType"
0x1400364b7  mov     [rsp+40h+var_20], rax; void *
0x1400364bc  mov     rcx, r14; SourceString
0x1400364bf  call    NfsReadUserRegistry
0x1400364c4  test    eax, eax
0x1400364c6  js      short loc_1400364D6
0x1400364c8  cmp     [rbp+arg_0], 1
0x1400364cc  mov     eax, esi
0x1400364ce  setnbe  al
0x1400364d1  inc     eax
0x1400364d3  mov     [rbx+1Ch], eax
0x1400364d6  lea     rax, [rbp+arg_0]
0x1400364da  mov     dword ptr [rbx+20h], 1EDh
0x1400364e1  lea     rdi, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1400364e8  mov     [rsp+40h+var_20], rax; void *
0x1400364ed  mov     rdx, rdi; PCWSTR
0x1400364f0  lea     r8, aAccess; "Access"
0x1400364f7  mov     rcx, r14; SourceString
0x1400364fa  call    NfsReadUserRegistry
0x1400364ff  test    eax, eax
0x140036501  js      short loc_140036509
0x140036503  mov     eax, [rbp+arg_0]
0x140036506  mov     [rbx+20h], eax
0x140036509  or      dword ptr [rbx+38h], 39Ch
0x140036510  lea     rax, [rbp+arg_0]
0x140036514  lea     r8, aSymlinks; "SymLinks"
0x14003651b  mov     [rsp+40h+var_20], rax; void *
0x140036520  mov     rdx, rdi; PCWSTR
0x140036523  mov     rcx, r14; SourceString
0x140036526  call    NfsReadUserRegistry
0x14003652b  test    eax, eax
0x14003652d  js      short loc_140036539
0x14003652f  cmp     [rbp+arg_0], esi
0x140036532  jnz     short loc_140036539
0x140036534  btr     dword ptr [rbx+38h], 9
0x140036539  lea     rax, [rbp+arg_0]
0x14003653d  mov     rdx, rdi; PCWSTR
0x140036540  lea     r8, aFileattributec; "FileAttributeCache"
0x140036547  mov     [rsp+40h+var_20], rax; void *
0x14003654c  mov     rcx, r14; SourceString
0x14003654f  call    NfsReadUserRegistry
0x140036554  test    eax, eax
0x140036556  js      short loc_140036561
0x140036558  cmp     [rbp+arg_0], esi
0x14003655b  jnz     short loc_140036561
0x14003655d  and     dword ptr [rbx+38h], 0FFFFFFEFh
0x140036561  lea     rax, [rbp+arg_0]
0x140036565  mov     rdx, rdi; PCWSTR
0x140036568  lea     r8, aNfslookup; "NFSLookup"
0x14003656f  mov     [rsp+40h+var_20], rax; void *
0x140036574  mov     rcx, r14; SourceString
0x140036577  call    NfsReadUserRegistry
0x14003657c  test    eax, eax
0x14003657e  js      short loc_14003658A
0x140036580  cmp     [rbp+arg_0], esi
0x140036583  jnz     short loc_14003658A
0x140036585  btr     dword ptr [rbx+38h], 7
0x14003658a  lea     rax, [rbp+arg_0]
0x14003658e  mov     rdx, rdi; PCWSTR
0x140036591  lea     r8, aNfsreaddir; "NFSReaddir"
0x140036598  mov     [rsp+40h+var_20], rax; void *
0x14003659d  mov     rcx, r14; SourceString
0x1400365a0  call    NfsReadUserRegistry
0x1400365a5  test    eax, eax
0x1400365a7  js      short loc_1400365B3
0x1400365a9  cmp     [rbp+arg_0], esi
0x1400365ac  jnz     short loc_1400365B3
0x1400365ae  btr     dword ptr [rbx+38h], 8
0x1400365b3  lea     rax, [rbp+arg_0]
0x1400365b7  mov     rdx, rdi; PCWSTR
0x1400365ba  lea     r8, aRemotewritecac; "RemoteWriteCache"
0x1400365c1  mov     [rsp+40h+var_20], rax; void *
0x1400365c6  mov     rcx, r14; SourceString
0x1400365c9  call    NfsReadUserRegistry
0x1400365ce  test    eax, eax
0x1400365d0  js      short loc_1400365DB
0x1400365d2  cmp     [rbp+arg_0], esi
0x1400365d5  jnz     short loc_1400365DB
0x1400365d7  and     dword ptr [rbx+38h], 0FFFFFFF7h
0x1400365db  lea     rax, [rbp+arg_0]
0x1400365df  mov     rdx, rdi; PCWSTR
0x1400365e2  lea     r8, aLocking; "Locking"
0x1400365e9  mov     [rsp+40h+var_20], rax; void *
0x1400365ee  mov     rcx, r14; SourceString
0x1400365f1  call    NfsReadUserRegistry
0x1400365f6  test    eax, eax
0x1400365f8  js      short loc_140036603
0x1400365fa  cmp     [rbp+arg_0], esi
0x1400365fd  jz      short loc_140036603
0x1400365ff  or      dword ptr [rbx+38h], 1
0x140036603  lea     rax, [rbp+arg_0]
0x140036607  mov     rdx, rdi; PCWSTR
0x14003660a  lea     r8, aDeletesymlinks; "DeleteSymlinks"
0x140036611  mov     [rsp+40h+var_20], rax; void *
0x140036616  mov     rcx, r14; SourceString
0x140036619  call    NfsReadUserRegistry
0x14003661e  test    eax, eax
0x140036620  js      short loc_14003662C
0x140036622  cmp     [rbp+arg_0], esi
0x140036625  jz      short loc_14003662C
0x140036627  bts     dword ptr [rbx+38h], 0Ch
0x14003662c  lea     rax, [rbp+arg_0]
0x140036630  mov     rdx, rdi; PCWSTR
0x140036633  lea     r8, aDisplayalllink; "DisplayAllLinks"
0x14003663a  mov     [rsp+40h+var_20], rax; void *
0x14003663f  mov     rcx, r14; SourceString
0x140036642  call    NfsReadUserRegistry
0x140036647  test    eax, eax
0x140036649  js      short loc_140036655
0x14003664b  cmp     [rbp+arg_0], esi
0x14003664e  jz      short loc_140036655
0x140036650  bts     dword ptr [rbx+38h], 0Bh
0x140036655  lea     rax, [rbp+arg_0]
0x140036659  mov     rdx, rdi; PCWSTR
0x14003665c  lea     r8, aEucmount; "EUCMount"
0x140036663  mov     [rsp+40h+var_20], rax; void *
0x140036668  mov     rcx, r14; SourceString
0x14003666b  call    NfsReadUserRegistry
0x140036670  test    eax, eax
0x140036672  js      short loc_1400366B0
0x140036674  mov     eax, [rbp+arg_0]
0x140036677  cmp     eax, 40h ; '@'
0x14003667a  jz      short loc_1400366AD
0x14003667c  cmp     eax, 2000h
0x140036681  jz      short loc_1400366AD
0x140036683  cmp     eax, 4000h
0x140036688  jz      short loc_1400366AD
0x14003668a  cmp     eax, 8000h
0x14003668f  jz      short loc_1400366AD
0x140036691  cmp     eax, 10000h
0x140036696  jz      short loc_1400366AD
0x140036698  cmp     eax, 20000h
0x14003669d  jz      short loc_1400366AD
0x14003669f  cmp     eax, 40000h
0x1400366a4  jz      short loc_1400366AD
0x1400366a6  cmp     eax, 80000h
0x1400366ab  jnz     short loc_1400366B0
0x1400366ad  or      [rbx+38h], eax
0x1400366b0  lea     rax, [rbp+arg_0]
0x1400366b4  mov     [rbp+arg_0], esi
0x1400366b7  lea     r8, aSecflavors; "SecFlavors"
0x1400366be  mov     [rsp+40h+var_20], rax; void *
0x1400366c3  mov     rdx, rdi; PCWSTR
0x1400366c6  mov     rcx, r14; SourceString
0x1400366c9  call    NfsReadUserRegistry
0x1400366ce  mov     ecx, [rbp+arg_0]
0x1400366d1  mov     edi, eax
0x1400366d3  mov     eax, 0Fh
0x1400366d8  and     ecx, eax
0x1400366da  cmovz   ecx, eax
0x1400366dd  mov     [rbx+3Ch], ecx
0x1400366e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400366e7  lea     rsi, WPP_GLOBAL_Control
0x1400366ee  cmp     rcx, rsi
0x1400366f1  jz      short loc_14003675A
0x1400366f3  mov     eax, [rcx+2Ch]
0x1400366f6  test    al, 4
0x1400366f8  jz      short loc_14003672F
0x1400366fa  mov     eax, [rbx+1Ch]
0x1400366fd  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x140036704  mov     r9d, [rbx+0Ch]
0x140036708  mov     edx, 18h
0x14003670d  mov     rcx, [rcx+18h]
0x140036711  mov     [rsp+40h+var_8], eax
0x140036715  mov     eax, [rbx+18h]
0x140036718  mov     [rsp+40h+var_10], eax
0x14003671c  mov     eax, [rbx+14h]
0x14003671f  mov     [rsp+40h+var_18], eax
0x140036723  mov     eax, [rbx+10h]
0x140036726  mov     dword ptr [rsp+40h+var_20], eax
0x14003672a  call    WPP_SF_ddddd
0x14003672f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036736  cmp     rcx, rsi
0x140036739  jz      short loc_14003675A
0x14003673b  mov     eax, [rcx+2Ch]
0x14003673e  test    al, 8
0x140036740  jz      short loc_14003675A
0x140036742  mov     rcx, [rcx+18h]
0x140036746  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003674d  mov     edx, 19h
0x140036752  mov     r9d, edi
0x140036755  call    WPP_SF_d
0x14003675a  lea     r11, [rsp+40h+var_s0]
0x14003675f  mov     eax, edi
0x140036761  mov     rbx, [r11+38h]
0x140036765  mov     rsi, [r11+40h]
0x140036769  mov     rsp, r11
0x14003676c  pop     r15
0x14003676e  pop     r14
0x140036770  pop     r12
0x140036772  pop     rdi
0x140036773  pop     rbp
0x140036774  retn
```
