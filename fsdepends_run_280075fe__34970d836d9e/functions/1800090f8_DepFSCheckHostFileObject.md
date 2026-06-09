# DepFSCheckHostFileObject

- ea: `0x1800090f8`
- end: `0x1800095fa`
- name: `DepFSCheckHostFileObject`
- size: `1282`
- prototype: `__int64 __fastcall(HANDLE FileHandle, PFILE_OBJECT pFileObject)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009840`
- `0x18000db70`

## callees

- `0x180001020`
- `0x1800012e8`
- `0x180001430`
- `0x180001460`
- `0x180009060`
- `0x1800090f8`
- `0x180009600`

## import_xrefs

- `ntoskrnl!FsRtlMupGetProviderIdFromName` at `0x1800094b4`
- `ntoskrnl!FsRtlMupGetProviderIdFromName` at `0x1800094b4`
- `ntoskrnl!FsRtlMupGetProviderInfoFromFileObject` at `0x1800094d0`
- `ntoskrnl!FsRtlMupGetProviderInfoFromFileObject` at `0x1800094d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800092fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009322`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009349`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009370`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800093d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009401`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000949d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800092fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009322`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009349`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009370`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800093d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009401`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000949d`

## pseudocode

```c
__int64 __fastcall DepFSCheckHostFileObject(HANDLE FileHandle, PFILE_OBJECT pFileObject, __int16 a3)
{
  unsigned __int64 DeviceType; // r9
  __int64 v7; // rdx
  unsigned int ProviderInfoFromFileObject; // ebx
  PDEVICE_OBJECT v9; // rcx
  unsigned __int16 v10; // dx
  int v11; // r9d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  ULONG pBufferSize; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-20h] BYREF
  int pBuffer; // [rsp+88h] [rbp+30h] BYREF

  if ( !Driver )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Au,
        (__int64)WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids,
        -1073741436);
    }
    return 3221225860LL;
  }
  if ( !pFileObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_D(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Bu,
        (__int64)WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids,
        -1073741811);
    }
    return 3221225485LL;
  }
  DeviceType = pFileObject->DeviceObject->DeviceType;
  if ( (unsigned int)DeviceType <= 0x24 && (v7 = 0x1000100080LL, _bittest64(&v7, DeviceType)) )
  {
    if ( byte_18000519A && (a3 & 0x210) == 0 )
    {
      ProviderInfoFromFileObject = -1073740761;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return ProviderInfoFromFileObject;
      }
      v10 = 29;
      goto LABEL_21;
    }
    if ( byte_180005195 || byte_180005194 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids,
          (unsigned __int8)byte_180005195,
          (unsigned __int8)byte_180005194);
      }
      return (unsigned int)-1073741431;
    }
    ProviderInfoFromFileObject = 0;
    if ( (_DWORD)DeviceType == 20 )
    {
      if ( (a3 & 0x10) == 0 )
      {
        if ( !FileHandle )
          return ProviderInfoFromFileObject;
        pBufferSize = 4;
        pBuffer = 0;
        if ( !pProviderId )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"\\Device\\LanmanRedirector");
          FsRtlMupGetProviderIdFromName(&DestinationString, &pProviderId);
        }
        ProviderInfoFromFileObject = FsRtlMupGetProviderInfoFromFileObject(pFileObject, 1u, &pBuffer, &pBufferSize);
        if ( (ProviderInfoFromFileObject & 0x80000000) != 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return ProviderInfoFromFileObject;
          }
          v10 = 35;
          v11 = ProviderInfoFromFileObject;
          goto LABEL_22;
        }
        if ( pBuffer == pProviderId )
          return (unsigned int)DepFSCheckSmbLoopback(FileHandle);
        ProviderInfoFromFileObject = -1073740761;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return ProviderInfoFromFileObject;
        }
        v10 = 36;
LABEL_21:
        v11 = -1073740761;
LABEL_22:
        WPP_SF_D((__int64)v9->AttachedDevice, v10, (__int64)WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids, v11);
        return ProviderInfoFromFileObject;
      }
      ProviderInfoFromFileObject = -1073740761;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return ProviderInfoFromFileObject;
      }
      v13 = 34;
LABEL_33:
      WPP_SF_(v12->AttachedDevice, v13, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids);
      return ProviderInfoFromFileObject;
    }
    DestinationString = 0;
    if ( (_DWORD)DeviceType != 7 && (_DWORD)DeviceType != 36 )
    {
      if ( (a3 & 0x10) != 0 )
      {
        ProviderInfoFromFileObject = -1073740761;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return ProviderInfoFromFileObject;
        }
        v13 = 31;
      }
      else
      {
        ProviderInfoFromFileObject = -1073740761;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return ProviderInfoFromFileObject;
        }
        v13 = 33;
      }
      goto LABEL_33;
    }
    RtlInitUnicodeString(&DestinationString, L"\\FileSystem\\Ntfs");
    if ( (unsigned __int8)DepFSCheckFileSystemNameForMatch(pFileObject, &DestinationString) )
      return ProviderInfoFromFileObject;
    RtlInitUnicodeString(&DestinationString, L"\\FileSystem\\exfat");
    if ( (unsigned __int8)DepFSCheckFileSystemNameForMatch(pFileObject, &DestinationString) )
      DepFSCheckRamdiskBoot(pFileObject);
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids,
        DeviceType,
        -1073740761);
    }
    return 3221226535LL;
  }
}

```

## disassembly

```asm
0x1800090f8  push    rbp
0x1800090fa  push    rbx
0x1800090fb  push    rsi
0x1800090fc  push    rdi
0x1800090fd  mov     rbp, rsp
0x180009100  sub     rsp, 58h
0x180009104  cmp     cs:Driver, 0
0x18000910c  mov     r10, r9
0x18000910f  mov     rdi, rdx
0x180009112  mov     rsi, rcx
0x180009115  jnz     short loc_18000915C
0x180009117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000911e  lea     rax, WPP_GLOBAL_Control
0x180009125  cmp     rcx, rax
0x180009128  jz      short loc_180009152
0x18000912a  mov     eax, [rcx+2Ch]
0x18000912d  test    al, 1
0x18000912f  jz      short loc_180009152
0x180009131  cmp     byte ptr [rcx+29h], 2
0x180009135  jb      short loc_180009152
0x180009137  mov     rcx, [rcx+18h]
0x18000913b  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x180009142  mov     edx, 1Ah
0x180009147  mov     r9d, 0C0000184h
0x18000914d  call    WPP_SF_D
0x180009152  mov     eax, 0C0000184h
0x180009157  jmp     loc_1800095F0
0x18000915c  test    rdi, rdi
0x18000915f  jnz     short loc_1800091A4
0x180009161  mov     rcx, cs:WPP_GLOBAL_Control
0x180009168  lea     rax, WPP_GLOBAL_Control
0x18000916f  cmp     rcx, rax
0x180009172  jz      short loc_18000919A
0x180009174  mov     eax, [rcx+2Ch]
0x180009177  test    al, 1
0x180009179  jz      short loc_18000919A
0x18000917b  cmp     byte ptr [rcx+29h], 2
0x18000917f  jb      short loc_18000919A
0x180009181  mov     rcx, [rcx+18h]
0x180009185  lea     edx, [rdi+1Bh]
0x180009188  mov     r9d, 0C000000Dh
0x18000918e  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x180009195  call    WPP_SF_D
0x18000919a  mov     eax, 0C000000Dh
0x18000919f  jmp     loc_1800095F0
0x1800091a4  mov     rcx, [rdx+8]
0x1800091a8  mov     r9d, [rcx+48h]
0x1800091ac  cmp     r9d, 24h ; '$'
0x1800091b0  ja      loc_1800095AE
0x1800091b6  mov     rdx, 1000100080h
0x1800091c0  bt      rdx, r9
0x1800091c4  jnb     loc_1800095AE
0x1800091ca  cmp     cs:byte_18000519A, 0
0x1800091d1  jz      short loc_18000922D
0x1800091d3  test    r8d, 210h
0x1800091da  jnz     short loc_18000922D
0x1800091dc  mov     ebx, 0C0000427h
0x1800091e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091e8  lea     rax, WPP_GLOBAL_Control
0x1800091ef  cmp     rcx, rax
0x1800091f2  jz      loc_1800095AA
0x1800091f8  mov     eax, [rcx+2Ch]
0x1800091fb  test    al, 1
0x1800091fd  jz      loc_1800095AA
0x180009203  cmp     byte ptr [rcx+29h], 2
0x180009207  jb      loc_1800095AA
0x18000920d  mov     edx, 1Dh
0x180009212  mov     r9d, 0C0000427h
0x180009218  mov     rcx, [rcx+18h]
0x18000921c  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x180009223  call    WPP_SF_D
0x180009228  jmp     loc_1800095AA
0x18000922d  movzx   edx, cs:byte_180005195
0x180009234  test    dl, dl
0x180009236  jnz     loc_180009562
0x18000923c  cmp     cs:byte_180005194, dl
0x180009242  jnz     loc_180009562
0x180009248  xor     ebx, ebx
0x18000924a  cmp     r9d, 14h
0x18000924e  jz      loc_18000942F
0x180009254  xorps   xmm0, xmm0
0x180009257  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000925b  cmp     r9d, 7
0x18000925f  jz      loc_1800093CB
0x180009265  cmp     r9d, 24h ; '$'
0x180009269  jz      loc_1800093CB
0x18000926f  bt      r8d, 4
0x180009274  jnb     short loc_1800092C1
0x180009276  mov     ebx, 0C0000427h
0x18000927b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009282  lea     rax, WPP_GLOBAL_Control
0x180009289  cmp     rcx, rax
0x18000928c  jz      loc_1800095AA
0x180009292  mov     eax, [rcx+2Ch]
0x180009295  test    al, 1
0x180009297  jz      loc_1800095AA
0x18000929d  cmp     byte ptr [rcx+29h], 2
0x1800092a1  jb      loc_1800095AA
0x1800092a7  mov     edx, 1Fh
0x1800092ac  mov     rcx, [rcx+18h]
0x1800092b0  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x1800092b7  call    WPP_SF_
0x1800092bc  jmp     loc_1800095AA
0x1800092c1  mov     eax, r9d
0x1800092c4  cmp     r9d, 7
0x1800092c8  jz      short loc_1800092D3
0x1800092ca  cmp     eax, 24h ; '$'
0x1800092cd  jnz     loc_180009390
0x1800092d3  mov     ecx, [r10]
0x1800092d6  lea     eax, [rcx-2]
0x1800092d9  cmp     eax, 2
0x1800092dc  jbe     short loc_1800092F0
0x1800092de  cmp     ecx, 1
0x1800092e1  jnz     loc_180009390
0x1800092e7  lea     rdx, SourceString; "\\FileSystem\\RAW"
0x1800092ee  jmp     short loc_180009345
0x1800092f0  lea     rdx, SourceString; "\\FileSystem\\RAW"
0x1800092f7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800092fb  call    cs:__imp_RtlInitUnicodeString
0x180009302  nop     dword ptr [rax+rax+00h]
0x180009307  lea     rdx, [rbp+DestinationString]
0x18000930b  mov     rcx, rdi
0x18000930e  call    DepFSCheckFileSystemNameForMatch
0x180009313  test    al, al
0x180009315  jnz     short loc_180009390
0x180009317  lea     rdx, aFilesystemExfa; "\\FileSystem\\exfat"
0x18000931e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009322  call    cs:__imp_RtlInitUnicodeString
0x180009329  nop     dword ptr [rax+rax+00h]
0x18000932e  lea     rdx, [rbp+DestinationString]
0x180009332  mov     rcx, rdi
0x180009335  call    DepFSCheckFileSystemNameForMatch
0x18000933a  test    al, al
0x18000933c  jnz     short loc_180009390
0x18000933e  lea     rdx, aFilesystemFast; "\\FileSystem\\Fastfat"
0x180009345  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009349  call    cs:__imp_RtlInitUnicodeString
0x180009350  nop     dword ptr [rax+rax+00h]
0x180009355  lea     rdx, [rbp+DestinationString]
0x180009359  mov     rcx, rdi
0x18000935c  call    DepFSCheckFileSystemNameForMatch
0x180009361  test    al, al
0x180009363  jnz     short loc_180009390
0x180009365  lea     rdx, aFilesystemUdfs; "\\FileSystem\\Udfs"
0x18000936c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009370  call    cs:__imp_RtlInitUnicodeString
0x180009377  nop     dword ptr [rax+rax+00h]
0x18000937c  lea     rdx, [rbp+DestinationString]
0x180009380  mov     rcx, rdi
0x180009383  call    DepFSCheckFileSystemNameForMatch
0x180009388  test    al, al
0x18000938a  jz      loc_1800095AA
0x180009390  mov     ebx, 0C0000427h
0x180009395  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939c  lea     rax, WPP_GLOBAL_Control
0x1800093a3  cmp     rcx, rax
0x1800093a6  jz      loc_1800095AA
0x1800093ac  mov     eax, [rcx+2Ch]
0x1800093af  test    al, 1
0x1800093b1  jz      loc_1800095AA
0x1800093b7  cmp     byte ptr [rcx+29h], 2
0x1800093bb  jb      loc_1800095AA
0x1800093c1  mov     edx, 21h ; '!'
0x1800093c6  jmp     loc_1800092AC
0x1800093cb  lea     rdx, aFilesystemNtfs; "\\FileSystem\\Ntfs"
0x1800093d2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800093d6  call    cs:__imp_RtlInitUnicodeString
0x1800093dd  nop     dword ptr [rax+rax+00h]
0x1800093e2  lea     rdx, [rbp+DestinationString]
0x1800093e6  mov     rcx, rdi
0x1800093e9  call    DepFSCheckFileSystemNameForMatch
0x1800093ee  test    al, al
0x1800093f0  jnz     loc_1800095AA
0x1800093f6  lea     rdx, aFilesystemExfa; "\\FileSystem\\exfat"
0x1800093fd  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009401  call    cs:__imp_RtlInitUnicodeString
0x180009408  nop     dword ptr [rax+rax+00h]
0x18000940d  lea     rdx, [rbp+DestinationString]
0x180009411  mov     rcx, rdi
0x180009414  call    DepFSCheckFileSystemNameForMatch
0x180009419  test    al, al
0x18000941b  jz      short loc_180009425
0x18000941d  mov     rcx, rdi
0x180009420  call    DepFSCheckRamdiskBoot
0x180009425  mov     eax, 1
0x18000942a  jmp     loc_1800095F0
0x18000942f  and     r8d, 10h
0x180009433  jz      short loc_180009470
0x180009435  mov     ebx, 0C0000427h
0x18000943a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009441  lea     rax, WPP_GLOBAL_Control
0x180009448  cmp     rcx, rax
0x18000944b  jz      loc_1800095AA
0x180009451  mov     eax, [rcx+2Ch]
0x180009454  test    al, 1
0x180009456  jz      loc_1800095AA
0x18000945c  cmp     byte ptr [rcx+29h], 2
0x180009460  jb      loc_1800095AA
0x180009466  mov     edx, 22h ; '"'
0x18000946b  jmp     loc_1800092AC
0x180009470  test    rsi, rsi
0x180009473  jz      loc_1800095AA
0x180009479  cmp     cs:pProviderId, ebx
0x18000947f  mov     [rbp+pBufferSize], 4
0x180009486  mov     [rbp+pBuffer], ebx
0x180009489  jnz     short loc_1800094C0
0x18000948b  xorps   xmm0, xmm0
0x18000948e  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector"
0x180009495  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009499  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000949d  call    cs:__imp_RtlInitUnicodeString
0x1800094a4  nop     dword ptr [rax+rax+00h]
0x1800094a9  lea     rdx, pProviderId; pProviderId
0x1800094b0  lea     rcx, [rbp+DestinationString]; pProviderName
0x1800094b4  call    cs:__imp_FsRtlMupGetProviderIdFromName
0x1800094bb  nop     dword ptr [rax+rax+00h]
0x1800094c0  lea     r9, [rbp+pBufferSize]; pBufferSize
0x1800094c4  mov     edx, 1; Level
0x1800094c9  lea     r8, [rbp+pBuffer]; pBuffer
0x1800094cd  mov     rcx, rdi; pFileObject
0x1800094d0  call    cs:__imp_FsRtlMupGetProviderInfoFromFileObject
0x1800094d7  nop     dword ptr [rax+rax+00h]
0x1800094dc  mov     ebx, eax
0x1800094de  test    eax, eax
0x1800094e0  jns     short loc_18000951C
0x1800094e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094e9  lea     rax, WPP_GLOBAL_Control
0x1800094f0  cmp     rcx, rax
0x1800094f3  jz      loc_1800095AA
0x1800094f9  mov     edx, [rcx+2Ch]
0x1800094fc  test    dl, 1
0x1800094ff  jz      loc_1800095AA
0x180009505  cmp     byte ptr [rcx+29h], 2
0x180009509  jb      loc_1800095AA
0x18000950f  mov     edx, 23h ; '#'
0x180009514  mov     r9d, ebx
0x180009517  jmp     loc_180009218
0x18000951c  mov     eax, cs:pProviderId
0x180009522  cmp     [rbp+pBuffer], eax
0x180009525  jz      short loc_180009556
0x180009527  mov     ebx, 0C0000427h
0x18000952c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009533  lea     rax, WPP_GLOBAL_Control
0x18000953a  cmp     rcx, rax
0x18000953d  jz      short loc_1800095AA
0x18000953f  mov     eax, [rcx+2Ch]
0x180009542  test    al, 1
0x180009544  jz      short loc_1800095AA
0x180009546  cmp     byte ptr [rcx+29h], 2
0x18000954a  jb      short loc_1800095AA
0x18000954c  mov     edx, 24h ; '$'
0x180009551  jmp     loc_180009212
0x180009556  mov     rcx, rsi; FileHandle
0x180009559  call    DepFSCheckSmbLoopback
0x18000955e  mov     ebx, eax
0x180009560  jmp     short loc_1800095AA
0x180009562  mov     rcx, cs:WPP_GLOBAL_Control
0x180009569  lea     rax, WPP_GLOBAL_Control
0x180009570  cmp     rcx, rax
0x180009573  jz      short loc_1800095A5
0x180009575  mov     eax, [rcx+2Ch]
0x180009578  test    al, 1
0x18000957a  jz      short loc_1800095A5
0x18000957c  cmp     byte ptr [rcx+29h], 2
0x180009580  jb      short loc_1800095A5
0x180009582  movzx   eax, cs:byte_180005194
0x180009589  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x180009590  mov     rcx, [rcx+18h]
0x180009594  mov     r9d, edx
0x180009597  mov     edx, 1Eh
0x18000959c  mov     [rsp+58h+var_38], eax
0x1800095a0  call    WPP_SF_DD
0x1800095a5  mov     ebx, 0C0000189h
0x1800095aa  mov     eax, ebx
0x1800095ac  jmp     short loc_1800095F0
0x1800095ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095b5  lea     rax, WPP_GLOBAL_Control
0x1800095bc  cmp     rcx, rax
0x1800095bf  jz      short loc_1800095EB
0x1800095c1  mov     eax, [rcx+2Ch]
0x1800095c4  test    al, 1
0x1800095c6  jz      short loc_1800095EB
0x1800095c8  cmp     byte ptr [rcx+29h], 2
0x1800095cc  jb      short loc_1800095EB
0x1800095ce  mov     rcx, [rcx+18h]
0x1800095d2  lea     r8, WPP_89de4c9ab0183a893b206e6614efcf73_Traceguids
0x1800095d9  mov     edx, 1Ch
0x1800095de  mov     [rsp+58h+var_38], 0C0000427h
0x1800095e6  call    WPP_SF_DD
0x1800095eb  mov     eax, 0C0000427h
0x1800095f0  add     rsp, 58h
0x1800095f4  pop     rdi
0x1800095f5  pop     rsi
0x1800095f6  pop     rbx
0x1800095f7  pop     rbp
0x1800095f8  retn
```
