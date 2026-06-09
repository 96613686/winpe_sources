# FveCreatePersistentRequestsFolder(ushort const *)

- ea: `0x1800ee734`
- end: `0x1800ee887`
- name: `?FveCreatePersistentRequestsFolder@@YAJPEBG@Z`
- size: `339`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800eec64`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x180019128`
- `0x1800ee320`
- `0x1800ee734`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x1800ee7ca`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x1800ee7ca`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800ee795`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800ee795`
- `ntdll!RtlFreeUnicodeString` at `0x1800ee862`
- `ntdll!RtlFreeUnicodeString` at `0x1800ee862`

## pseudocode

```c
__int64 __fastcall FveCreatePersistentRequestsFolder(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  int v3; // eax
  int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  unsigned int SVIRequestFolder; // eax
  int v9; // ebx
  UNICODE_STRING VolumeRootPath; // [rsp+20h] [rbp-48h] BYREF

  VolumeRootPath = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  v3 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &VolumeRootPath, 0, 0);
  v4 = FromNtStatus(v3);
  if ( v4 >= 0 )
  {
    v7 = RtlCreateSystemVolumeInformationFolder(&VolumeRootPath);
    v4 = FromNtStatus(v7);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v6 = 152;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v6 = 151;
LABEL_12:
      WPP_SF_D(v5[2], v6, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, (unsigned int)v4);
      goto LABEL_13;
    }
  }
  do
  {
LABEL_13:
    SVIRequestFolder = FvePersistentRequest::CreateSVIRequestFolder(a1, *((_DWORD *)&g_persistentRequestsMap + 4 * v2));
    v9 = SVIRequestFolder;
    if ( SVIRequestFolder )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          SVIRequestFolder);
      if ( v9 < 0 )
        break;
    }
    ++v2;
  }
  while ( v2 < 4 );
  RtlFreeUnicodeString(&VolumeRootPath);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800ee734  push    rbx
0x1800ee736  push    rbp
0x1800ee737  push    rsi
0x1800ee738  push    rdi
0x1800ee739  sub     rsp, 48h
0x1800ee73d  mov     rax, cs:__security_cookie
0x1800ee744  xor     rax, rsp
0x1800ee747  mov     [rsp+68h+var_38], rax
0x1800ee74c  xorps   xmm0, xmm0
0x1800ee74f  mov     rsi, rcx
0x1800ee752  movups  xmmword ptr [rsp+68h+VolumeRootPath.Length], xmm0
0x1800ee757  xor     edi, edi
0x1800ee759  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee760  lea     rbp, WPP_GLOBAL_Control
0x1800ee767  cmp     rcx, rbp
0x1800ee76a  jz      short loc_1800EE787
0x1800ee76c  test    byte ptr [rcx+1Ch], 20h
0x1800ee770  jz      short loc_1800EE787
0x1800ee772  mov     rcx, [rcx+10h]
0x1800ee776  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee77d  mov     edx, 96h
0x1800ee782  call    WPP_SF_
0x1800ee787  xor     r9d, r9d
0x1800ee78a  lea     rdx, [rsp+68h+VolumeRootPath]
0x1800ee78f  xor     r8d, r8d
0x1800ee792  mov     rcx, rsi
0x1800ee795  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800ee79c  nop     dword ptr [rax+rax+00h]
0x1800ee7a1  mov     ecx, eax; int
0x1800ee7a3  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800ee7a8  test    eax, eax
0x1800ee7aa  jns     short loc_1800EE7C5
0x1800ee7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee7b3  cmp     rcx, rbp
0x1800ee7b6  jz      short loc_1800EE80B
0x1800ee7b8  test    byte ptr [rcx+1Ch], 2
0x1800ee7bc  jz      short loc_1800EE80B
0x1800ee7be  mov     edx, 97h
0x1800ee7c3  jmp     short loc_1800EE7F8
0x1800ee7c5  lea     rcx, [rsp+68h+VolumeRootPath]; VolumeRootPath
0x1800ee7ca  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x1800ee7d1  nop     dword ptr [rax+rax+00h]
0x1800ee7d6  mov     ecx, eax; int
0x1800ee7d8  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800ee7dd  test    eax, eax
0x1800ee7df  jns     short loc_1800EE80B
0x1800ee7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee7e8  cmp     rcx, rbp
0x1800ee7eb  jz      short loc_1800EE80B
0x1800ee7ed  test    byte ptr [rcx+1Ch], 2
0x1800ee7f1  jz      short loc_1800EE80B
0x1800ee7f3  mov     edx, 98h
0x1800ee7f8  mov     rcx, [rcx+10h]
0x1800ee7fc  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee803  mov     r9d, eax
0x1800ee806  call    WPP_SF_D
0x1800ee80b  lea     rax, ?g_persistentRequestsMap@@3PAU_FVE_PERSISTENT_REQUEST_CONFIG@@A; _FVE_PERSISTENT_REQUEST_CONFIG near * g_persistentRequestsMap
0x1800ee812  mov     edx, edi
0x1800ee814  add     rdx, rdx
0x1800ee817  mov     rcx, rsi
0x1800ee81a  mov     edx, [rax+rdx*8]
0x1800ee81d  call    ?CreateSVIRequestFolder@FvePersistentRequest@@SAJPEBGW4_FVE_REQUEST_TYPE@@@Z; FvePersistentRequest::CreateSVIRequestFolder(ushort const *,_FVE_REQUEST_TYPE)
0x1800ee822  mov     ebx, eax
0x1800ee824  test    eax, eax
0x1800ee826  jz      short loc_1800EE856
0x1800ee828  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ee82f  cmp     rcx, rbp
0x1800ee832  jz      short loc_1800EE852
0x1800ee834  test    byte ptr [rcx+1Ch], 40h
0x1800ee838  jz      short loc_1800EE852
0x1800ee83a  mov     rcx, [rcx+10h]
0x1800ee83e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ee845  mov     edx, 99h
0x1800ee84a  mov     r9d, eax
0x1800ee84d  call    WPP_SF_d
0x1800ee852  test    ebx, ebx
0x1800ee854  js      short loc_1800EE85D
0x1800ee856  inc     edi
0x1800ee858  cmp     edi, 4
0x1800ee85b  jb      short loc_1800EE80B
0x1800ee85d  lea     rcx, [rsp+68h+VolumeRootPath]; UnicodeString
0x1800ee862  call    cs:__imp_RtlFreeUnicodeString
0x1800ee869  nop     dword ptr [rax+rax+00h]
0x1800ee86e  mov     eax, ebx
0x1800ee870  mov     rcx, [rsp+68h+var_38]
0x1800ee875  xor     rcx, rsp; StackCookie
0x1800ee878  call    __security_check_cookie
0x1800ee87d  add     rsp, 48h
0x1800ee881  pop     rdi
0x1800ee882  pop     rsi
0x1800ee883  pop     rbp
0x1800ee884  pop     rbx
0x1800ee885  retn
```
