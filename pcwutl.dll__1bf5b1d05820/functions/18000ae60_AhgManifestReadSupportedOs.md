# AhgManifestReadSupportedOs

- ea: `0x18000ae60`
- end: `0x18000b041`
- name: `AhgManifestReadSupportedOs`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180009fe8`

## callees

- `0x18000ae60`
- `0x18000b048`
- `0x18000e240`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18000af0c`
- `KERNEL32!GetVersionExW` at `0x18000af0c`
- `KERNEL32!GetLastError` at `0x18000af16`
- `KERNEL32!GetLastError` at `0x18000af16`
- `ntdll!RtlFreeHeap` at `0x18000b011`
- `ntdll!RtlFreeHeap` at `0x18000b011`

## string_xrefs

- `0x18000aece`: `Failed to read manifest [%d]`
- `0x18000aee0`: `AhgManifestReadSupportedOs`
- `0x18000afeb`: `AhgManifestReadSupportedOs`
- `0x18000afde`: `No manifest to read`

## pseudocode

```c
__int64 __fastcall AhgManifestReadSupportedOs(_WORD *a1, void *a2)
{
  unsigned int LastError; // eax
  unsigned int *v5; // rbx
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // r8d
  unsigned int v11; // r10d
  unsigned int v12; // edx
  unsigned int i; // ebp
  __int64 v14; // rcx
  unsigned int v15; // r9d
  __int64 v16; // r11
  unsigned int v17; // r9d
  PVOID P[2]; // [rsp+30h] [rbp-158h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-148h] BYREF

  P[0] = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  LastError = AhgpManifestRead(P, a2, 6u);
  v5 = (unsigned int *)P[0];
  v6 = LastError;
  if ( LastError )
  {
    v7 = "Failed to read manifest [%d]";
    v8 = 187;
    v9 = 2;
LABEL_3:
    AslLogCallPrintf(v9, "AhgManifestReadSupportedOs", v8, v7, LastError);
    goto LABEL_21;
  }
  if ( P[0] && *(_DWORD *)P[0] )
  {
    if ( !GetVersionExW(&VersionInformation) )
    {
      LastError = GetLastError();
      v7 = "GetVersionEx failed [%d]";
      v8 = 203;
      v6 = LastError;
      v9 = 1;
      goto LABEL_3;
    }
    v10 = 0;
    v11 = 0;
    v12 = LOWORD(VersionInformation.dwMinorVersion) + (LOWORD(VersionInformation.dwMajorVersion) << 16);
    v6 = 2;
    for ( i = v12; v11 < *v5; ++v11 )
    {
      v14 = 8LL * v11;
      if ( v5[v14 + 6] == 1 )
      {
        v15 = 0;
        while ( 1 )
        {
          v16 = 4LL * v15;
          if ( *(_QWORD *)&v5[v14 + 2] == *(__int64 *)((char *)&SbSupportedOsList[v16] + 4)
            && *(_QWORD *)&v5[v14 + 4] == *(__int64 *)((char *)&SbSupportedOsList[v16 + 1] + 4) )
          {
            break;
          }
          if ( ++v15 >= 5 )
            goto LABEL_18;
        }
        v17 = HIWORD(SbSupportedOsList[v16 + 2]) + (WORD2(SbSupportedOsList[v16 + 2]) << 16);
        if ( v17 <= i && i - v17 < v12 )
        {
          v6 = 0;
          v12 = i - v17;
          v10 = HIWORD(SbSupportedOsList[v16 + 2]) + (WORD2(SbSupportedOsList[v16 + 2]) << 16);
        }
      }
LABEL_18:
      ;
    }
    a1[1] = (unsigned __int8)v10;
    *a1 = BYTE2(v10);
  }
  else
  {
    v6 = 2;
    AslLogCallPrintf(3, "AhgManifestReadSupportedOs", 193, "No manifest to read");
  }
LABEL_21:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v6;
}

```

## disassembly

```asm
0x18000ae60  mov     [rsp+arg_10], rbx
0x18000ae65  mov     [rsp+arg_18], rbp
0x18000ae6a  push    rsi
0x18000ae6b  push    rdi
0x18000ae6c  push    r15
0x18000ae6e  sub     rsp, 170h
0x18000ae75  mov     rax, cs:__security_cookie
0x18000ae7c  xor     rax, rsp
0x18000ae7f  mov     [rsp+188h+var_28], rax
0x18000ae87  mov     rbx, rdx
0x18000ae8a  mov     [rsp+188h+P], 0
0x18000ae93  mov     rsi, rcx
0x18000ae96  xor     edx, edx; Val
0x18000ae98  lea     rcx, [rsp+188h+VersionInformation.dwMajorVersion]; void *
0x18000ae9d  mov     r8d, 118h; Size
0x18000aea3  call    memset_0
0x18000aea8  mov     r8d, 6
0x18000aeae  mov     [rsp+188h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000aeb6  mov     rdx, rbx
0x18000aeb9  lea     rcx, [rsp+188h+P]
0x18000aebe  call    AhgpManifestRead
0x18000aec3  mov     rbx, [rsp+188h+P]
0x18000aec8  mov     edi, eax
0x18000aeca  test    eax, eax
0x18000aecc  jz      short loc_18000AEF5
0x18000aece  lea     r9, aFailedToReadMa; "Failed to read manifest [%d]"
0x18000aed5  mov     r8d, 0BBh
0x18000aedb  mov     ecx, 2
0x18000aee0  lea     rdx, aAhgmanifestrea; "AhgManifestReadSupportedOs"
0x18000aee7  mov     [rsp+188h+var_168], eax
0x18000aeeb  call    AslLogCallPrintf
0x18000aef0  jmp     loc_18000AFFA
0x18000aef5  test    rbx, rbx
0x18000aef8  jz      loc_18000AFD9
0x18000aefe  cmp     dword ptr [rbx], 0
0x18000af01  jz      loc_18000AFD9
0x18000af07  lea     rcx, [rsp+188h+VersionInformation]; lpVersionInformation
0x18000af0c  call    cs:__imp_GetVersionExW
0x18000af12  test    eax, eax
0x18000af14  jnz     short loc_18000AF32
0x18000af16  call    cs:__imp_GetLastError
0x18000af1c  lea     r9, aGetversionexFa; "GetVersionEx failed [%d]"
0x18000af23  mov     r8d, 0CBh
0x18000af29  mov     edi, eax
0x18000af2b  mov     ecx, 1
0x18000af30  jmp     short loc_18000AEE0
0x18000af32  movzx   edx, word ptr [rsp+188h+VersionInformation.dwMajorVersion]
0x18000af37  xor     r8d, r8d
0x18000af3a  movzx   eax, word ptr [rsp+188h+VersionInformation.dwMinorVersion]
0x18000af3f  xor     r10d, r10d
0x18000af42  shl     edx, 10h
0x18000af45  add     edx, eax
0x18000af47  lea     edi, [r8+2]
0x18000af4b  mov     ebp, edx
0x18000af4d  cmp     [rbx], r8d
0x18000af50  jbe     short loc_18000AFC4
0x18000af52  lea     r15, SbSupportedOsList
0x18000af59  mov     ecx, r10d
0x18000af5c  shl     rcx, 5
0x18000af60  cmp     dword ptr [rcx+rbx+18h], 1
0x18000af65  jnz     short loc_18000AFBC
0x18000af67  xor     r9d, r9d
0x18000af6a  mov     rax, [rcx+rbx+8]
0x18000af6f  mov     r11d, r9d
0x18000af72  shl     r11, 5
0x18000af76  cmp     rax, [r11+r15+4]
0x18000af7b  jnz     short loc_18000AF89
0x18000af7d  mov     rax, [rcx+rbx+10h]
0x18000af82  cmp     rax, [r11+r15+0Ch]
0x18000af87  jz      short loc_18000AF94
0x18000af89  inc     r9d
0x18000af8c  cmp     r9d, 5
0x18000af90  jb      short loc_18000AF6A
0x18000af92  jmp     short loc_18000AFBC
0x18000af94  movzx   r9d, word ptr [r11+r15+14h]
0x18000af9a  movzx   eax, word ptr [r11+r15+16h]
0x18000afa0  shl     r9d, 10h
0x18000afa4  add     r9d, eax
0x18000afa7  cmp     r9d, ebp
0x18000afaa  ja      short loc_18000AFBC
0x18000afac  mov     eax, ebp
0x18000afae  sub     eax, r9d
0x18000afb1  cmp     eax, edx
0x18000afb3  jnb     short loc_18000AFBC
0x18000afb5  xor     edi, edi
0x18000afb7  mov     edx, eax
0x18000afb9  mov     r8d, r9d
0x18000afbc  inc     r10d
0x18000afbf  cmp     r10d, [rbx]
0x18000afc2  jb      short loc_18000AF59
0x18000afc4  movzx   eax, r8b
0x18000afc8  shr     r8d, 10h
0x18000afcc  mov     [rsi+2], ax
0x18000afd0  movzx   eax, r8b
0x18000afd4  mov     [rsi], ax
0x18000afd7  jmp     short loc_18000AFFA
0x18000afd9  mov     edi, 2
0x18000afde  lea     r9, aNoManifestToRe; "No manifest to read"
0x18000afe5  mov     r8d, 0C1h
0x18000afeb  lea     rdx, aAhgmanifestrea; "AhgManifestReadSupportedOs"
0x18000aff2  lea     ecx, [rdi+1]
0x18000aff5  call    AslLogCallPrintf
0x18000affa  test    rbx, rbx
0x18000affd  jz      short loc_18000B017
0x18000afff  mov     rcx, gs:60h
0x18000b008  mov     r8, rbx; P
0x18000b00b  xor     edx, edx; Flags
0x18000b00d  mov     rcx, [rcx+30h]; HeapHandle
0x18000b011  call    cs:__imp_RtlFreeHeap
0x18000b017  mov     eax, edi
0x18000b019  mov     rcx, [rsp+188h+var_28]
0x18000b021  xor     rcx, rsp; StackCookie
0x18000b024  call    __security_check_cookie
0x18000b029  lea     r11, [rsp+188h+var_18]
0x18000b031  mov     rbx, [r11+30h]
0x18000b035  mov     rbp, [r11+38h]
0x18000b039  mov     rsp, r11
0x18000b03c  pop     r15
0x18000b03e  pop     rdi
0x18000b03f  pop     rsi
0x18000b040  retn
```
