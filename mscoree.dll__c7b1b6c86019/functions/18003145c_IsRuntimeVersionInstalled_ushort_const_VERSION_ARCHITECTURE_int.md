# IsRuntimeVersionInstalled(ushort const *,VERSION_ARCHITECTURE,int)

- ea: `0x18003145c`
- end: `0x18003160e`
- name: `?IsRuntimeVersionInstalled@@YAJPEBGW4VERSION_ARCHITECTURE@@H@Z`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009af4`
- `0x180029528`

## callees

- `0x180003070`
- `0x180003890`
- `0x180006130`
- `0x18000c1a8`
- `0x18000d614`
- `0x18003145c`
- `0x180041ac0`
- `0x180045030`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x18003158e`
- `KERNEL32!FindFirstFileW` at `0x1800315cd`
- `KERNEL32!FindFirstFileW` at `0x18003158e`
- `KERNEL32!FindFirstFileW` at `0x1800315cd`
- `KERNEL32!FindClose` at `0x18003159d`
- `KERNEL32!FindClose` at `0x18003159d`

## string_xrefs

- `0x1800314b6`: `\mscorwks.dll`
- `0x1800314d2`: `\clr.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsRuntimeVersionInstalled(wchar_t *a1, int a2, int a3)
{
  wchar_t *InstallRoot; // rcx
  int VersionDirectory; // ebx
  unsigned __int64 v7; // rax
  HANDLE FirstFileW; // rax
  wchar_t *v10; // [rsp+20h] [rbp-E0h] BYREF
  BOOL v11; // [rsp+28h] [rbp-D8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v13[12]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v14[20]; // [rsp+298h] [rbp+198h] BYREF
  wchar_t Source[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Destination[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  InstallRoot = GetInstallRoot(a2);
  v10 = InstallRoot;
  v11 = InstallRoot != 0;
  if ( !InstallRoot )
    goto LABEL_12;
  wcscpy(v14, L"\\mscwks.dll");
  wcscpy(v13, L"\\clr.dll");
  if ( !a1 )
    goto LABEL_12;
  VersionDirectory = CreateVersionDirectory(InstallRoot, a1, Source, 0x105u);
  if ( VersionDirectory >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    if ( v7 > 0xFFFFFFFFFFFFFFF1uLL
      || v7 + 14 > 0x105
      || (wcscpy_s(Destination, 0x105u, Source),
          wcscat_s(Source, 0x105u, v14),
          memset_thunk_772440563353939046(&FindFileData, 0, 0x250u),
          FirstFileW = FindFirstFileW(Source, &FindFileData),
          FirstFileW == (HANDLE)-1LL)
      && (!a3
       || (wcscat_s(Destination, 0x105u, v13),
           FirstFileW = FindFirstFileW(Destination, &FindFileData),
           FirstFileW == (HANDLE)-1LL)) )
    {
LABEL_12:
      VersionDirectory = 1;
      goto LABEL_13;
    }
    FindClose(FirstFileW);
    VersionDirectory = 0;
  }
LABEL_13:
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v10);
  return (unsigned int)VersionDirectory;
}

```

## disassembly

```asm
0x18003145c  mov     [rsp-8+arg_10], rbx
0x180031461  push    rbp
0x180031462  push    rsi
0x180031463  push    rdi
0x180031464  push    r14
0x180031466  push    r15
0x180031468  lea     rbp, [rsp-5F0h]
0x180031470  sub     rsp, 6F0h
0x180031477  mov     rax, cs:__security_cookie
0x18003147e  xor     rax, rsp
0x180031481  mov     [rbp+610h+var_30], rax
0x180031488  mov     edi, r8d
0x18003148b  mov     rbx, rcx
0x18003148e  mov     ecx, edx
0x180031490  call    ?GetInstallRoot@@YAPEAGW4VERSION_ARCHITECTURE@@@Z; GetInstallRoot(VERSION_ARCHITECTURE)
0x180031495  mov     rcx, rax; Source
0x180031498  mov     [rsp+710h+var_6F0], rax
0x18003149d  xor     esi, esi
0x18003149f  mov     eax, esi
0x1800314a1  lea     r15d, [rsi+1]
0x1800314a5  test    rcx, rcx
0x1800314a8  cmovnz  eax, r15d
0x1800314ac  mov     [rsp+710h+var_6E8], eax
0x1800314b0  jz      loc_1800315D9
0x1800314b6  movups  xmm0, xmmword ptr cs:aMscorwksDll_0; "\\mscorwks.dll"
0x1800314bd  movups  xmmword ptr [rbp+610h+var_478], xmm0
0x1800314c4  movups  xmm1, xmmword ptr cs:aMscorwksDll_0+0Ch; "wks.dll"
0x1800314cb  movups  xmmword ptr [rbp+610h+var_478+0Ch], xmm1
0x1800314d2  movups  xmm0, xmmword ptr cs:aClrDll; "\\clr.dll"
0x1800314d9  movups  xmmword ptr [rbp+610h+var_490], xmm0
0x1800314e0  movzx   eax, word ptr cs:aClrDll+10h; ""
0x1800314e7  mov     [rbp+610h+var_480], ax
0x1800314ee  test    rbx, rbx
0x1800314f1  jz      loc_1800315D9
0x1800314f7  mov     r14d, 105h
0x1800314fd  mov     r9d, r14d; SizeInWords
0x180031500  lea     r8, [rbp+610h+Source]; Destination
0x180031507  mov     rdx, rbx; wchar_t *
0x18003150a  call    ?CreateVersionDirectory@@YAJPEAGPEBG0_K@Z; CreateVersionDirectory(ushort *,ushort const *,ushort *,unsigned __int64)
0x18003150f  mov     ebx, eax
0x180031511  test    eax, eax
0x180031513  js      loc_1800315DC
0x180031519  lea     rcx, [rbp+610h+Source]
0x180031520  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031524  inc     rax
0x180031527  cmp     [rcx+rax*2], si
0x18003152b  jnz     short loc_180031524
0x18003152d  cmp     rax, 0FFFFFFFFFFFFFFF1h
0x180031531  ja      loc_1800315D9
0x180031537  add     rax, 0Eh
0x18003153b  cmp     rax, r14
0x18003153e  ja      loc_1800315D9
0x180031544  lea     r8, [rbp+610h+Source]; Source
0x18003154b  mov     rdx, r14; SizeInWords
0x18003154e  lea     rcx, [rbp+610h+Destination]; Destination
0x180031555  call    wcscpy_s
0x18003155a  lea     r8, [rbp+610h+var_478]; Source
0x180031561  mov     rdx, r14; SizeInWords
0x180031564  lea     rcx, [rbp+610h+Source]; Destination
0x18003156b  call    wcscat_s
0x180031570  xor     edx, edx; Val
0x180031572  mov     r8d, 250h; Size
0x180031578  lea     rcx, [rsp+710h+FindFileData]; void *
0x18003157d  call    memset$thunk$772440563353939046
0x180031582  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x180031587  lea     rcx, [rbp+610h+Source]; lpFileName
0x18003158e  call    cs:__imp_FindFirstFileW
0x180031594  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031598  jz      short loc_1800315A7
0x18003159a  mov     rcx, rax; hFindFile
0x18003159d  call    cs:__imp_FindClose
0x1800315a3  mov     ebx, esi
0x1800315a5  jmp     short loc_1800315DC
0x1800315a7  test    edi, edi
0x1800315a9  jz      short loc_1800315D9
0x1800315ab  lea     r8, [rbp+610h+var_490]; Source
0x1800315b2  mov     rdx, r14; SizeInWords
0x1800315b5  lea     rcx, [rbp+610h+Destination]; Destination
0x1800315bc  call    wcscat_s
0x1800315c1  lea     rdx, [rsp+710h+FindFileData]; lpFindFileData
0x1800315c6  lea     rcx, [rbp+610h+Destination]; lpFileName
0x1800315cd  call    cs:__imp_FindFirstFileW
0x1800315d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800315d7  jnz     short loc_18003159A
0x1800315d9  mov     ebx, r15d
0x1800315dc  lea     rcx, [rsp+710h+var_6F0]
0x1800315e1  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x1800315e6  mov     eax, ebx
0x1800315e8  mov     rcx, [rbp+610h+var_30]
0x1800315ef  xor     rcx, rsp; StackCookie
0x1800315f2  call    __security_check_cookie
0x1800315f7  mov     rbx, [rsp+710h+arg_10]
0x1800315ff  add     rsp, 6F0h
0x180031606  pop     r15
0x180031608  pop     r14
0x18003160a  pop     rdi
0x18003160b  pop     rsi
0x18003160c  pop     rbp
0x18003160d  retn
```
