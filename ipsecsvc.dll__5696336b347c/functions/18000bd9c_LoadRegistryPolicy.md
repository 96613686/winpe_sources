# LoadRegistryPolicy

- ea: `0x18000bd9c`
- end: `0x18000becd`
- name: `LoadRegistryPolicy`
- size: `305`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d2ec`

## callees

- `0x18000bd9c`
- `0x18000e510`
- `0x18000f638`
- `0x180019d80`
- `0x18003947c`
- `0x180039c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bebb`

## pseudocode

```c
__int64 __fastcall LoadRegistryPolicy(int a1, _QWORD *a2)
{
  void *v4; // rcx
  unsigned int PolicyObjectFromRegistry; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  PolicyObjectFromRegistry = OpenRegistryIPSECRootKey(
                               (__int64)v4,
                               L"SOFTWARE\\Policies\\Microsoft\\Windows\\IPSEC\\Policy\\Local",
                               &hKey);
  v6 = PolicyObjectFromRegistry;
  if ( PolicyObjectFromRegistry )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 79;
LABEL_12:
        WPP_SF_d(v7[2], v8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, PolicyObjectFromRegistry);
        v7 = WPP_GLOBAL_Control;
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    goto LABEL_16;
  }
  PolicyObjectFromRegistry = ReadPolicyObjectFromRegistry(hKey);
  v6 = PolicyObjectFromRegistry;
  if ( PolicyObjectFromRegistry )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 80;
        goto LABEL_12;
      }
LABEL_13:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
        WPP_SF_SD(v7[2], 81, (unsigned int)WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, a1, v6);
    }
LABEL_16:
    *a2 = 0;
    goto LABEL_18;
  }
  *a2 = 0;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000bd9c  mov     rax, rsp
0x18000bd9f  push    rbx
0x18000bda0  push    rsi
0x18000bda1  push    rdi
0x18000bda2  push    r14
0x18000bda4  sub     rsp, 48h
0x18000bda8  mov     rdi, rdx
0x18000bdab  mov     qword ptr [rax+20h], 0
0x18000bdb3  mov     rsi, rcx
0x18000bdb6  mov     qword ptr [rax-38h], 0
0x18000bdbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdc5  lea     r14, WPP_GLOBAL_Control
0x18000bdcc  cmp     rcx, r14
0x18000bdcf  jz      short loc_18000BDEC
0x18000bdd1  test    byte ptr [rcx+1Ch], 4
0x18000bdd5  jz      short loc_18000BDEC
0x18000bdd7  mov     rcx, [rcx+10h]
0x18000bddb  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000bde2  mov     edx, 4Dh ; 'M'
0x18000bde7  call    WPP_SF_
0x18000bdec  lea     r8, [rsp+68h+hKey]
0x18000bdf4  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000bdfb  call    OpenRegistryIPSECRootKey
0x18000be00  mov     ebx, eax
0x18000be02  test    eax, eax
0x18000be04  jz      short loc_18000BE23
0x18000be06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be0d  cmp     rcx, r14
0x18000be10  jz      loc_18000BE9D
0x18000be16  test    byte ptr [rcx+1Ch], 10h
0x18000be1a  jz      short loc_18000BE76
0x18000be1c  mov     edx, 4Fh ; 'O'
0x18000be21  jmp     short loc_18000BE5C
0x18000be23  mov     rcx, [rsp+68h+hKey]; hKey
0x18000be2b  lea     r9, [rsp+68h+var_38]
0x18000be30  lea     r8, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18000be37  mov     rdx, rsi
0x18000be3a  call    ReadPolicyObjectFromRegistry
0x18000be3f  mov     ebx, eax
0x18000be41  test    eax, eax
0x18000be43  jz      short loc_18000BEA6
0x18000be45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be4c  cmp     rcx, r14
0x18000be4f  jz      short loc_18000BE9D
0x18000be51  test    byte ptr [rcx+1Ch], 10h
0x18000be55  jz      short loc_18000BE76
0x18000be57  mov     edx, 50h ; 'P'
0x18000be5c  mov     rcx, [rcx+10h]
0x18000be60  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000be67  mov     r9d, eax
0x18000be6a  call    WPP_SF_d
0x18000be6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be76  cmp     rcx, r14
0x18000be79  jz      short loc_18000BE9D
0x18000be7b  test    byte ptr [rcx+1Ch], 10h
0x18000be7f  jz      short loc_18000BE9D
0x18000be81  mov     rcx, [rcx+10h]
0x18000be85  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18000be8c  mov     edx, 51h ; 'Q'
0x18000be91  mov     [rsp+68h+var_48], ebx
0x18000be95  mov     r9, rsi
0x18000be98  call    WPP_SF_SD
0x18000be9d  mov     qword ptr [rdi], 0
0x18000bea4  jmp     short loc_18000BEAE
0x18000bea6  mov     rax, [rsp+68h+var_38]
0x18000beab  mov     [rdi], rax
0x18000beae  mov     rcx, [rsp+68h+hKey]; hKey
0x18000beb6  test    rcx, rcx
0x18000beb9  jz      short loc_18000BEC1
0x18000bebb  call    cs:__imp_RegCloseKey
0x18000bec1  mov     eax, ebx
0x18000bec3  add     rsp, 48h
0x18000bec7  pop     r14
0x18000bec9  pop     rdi
0x18000beca  pop     rsi
0x18000becb  pop     rbx
0x18000becc  retn
```
