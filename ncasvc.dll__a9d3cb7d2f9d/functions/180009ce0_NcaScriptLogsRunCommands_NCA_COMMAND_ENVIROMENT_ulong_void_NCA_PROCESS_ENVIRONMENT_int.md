# NcaScriptLogsRunCommands(NCA_COMMAND_ENVIROMENT_ *,ulong,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)

- ea: `0x180009ce0`
- end: `0x180009f16`
- name: `?NcaScriptLogsRunCommands@@YAKPEAUNCA_COMMAND_ENVIROMENT_@@KPEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z`
- size: `566`
- prototype: `__int64 __fastcall(struct NCA_COMMAND_ENVIROMENT_ *, unsigned int, void *, void **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a398`

## callees

- `0x180003770`
- `0x180004f34`
- `0x180009ce0`
- `0x180009f1c`
- `0x180019520`
- `0x180019784`
- `0x180019b04`

## string_xrefs

- `0x180009d1c`: ` -Command "& { $global:FormatEnumerationLimit=-1; `

## pseudocode

```c
__int64 __fastcall NcaScriptLogsRunCommands(
        struct NCA_COMMAND_ENVIROMENT_ *a1,
        unsigned int a2,
        void *a3,
        void **a4,
        int *a5)
{
  int v9; // eax
  unsigned int started; // ebx
  void *v11; // rdi
  __int64 v12; // rbx
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  int ExpandedCanonicalLongPathName; // eax
  int v20; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR lpCommandLine; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR lpApplicationName; // [rsp+48h] [rbp-8h] BYREF

  lpMem = 0;
  lpCommandLine = 0;
  lpApplicationName = 0;
  v20 = 0;
  v9 = NcaStringBuild(&lpMem, L" -Command \"& { $global:FormatEnumerationLimit=-1; ", 0);
  if ( v9 >= 0 )
  {
    v11 = lpMem;
    v12 = 0;
    while ( (unsigned int)v12 < a2 )
    {
      v13 = NcaStringBuild(&lpCommandLine, v11, *((_QWORD *)a1 + 3 * v12 + 2));
      if ( v13 < 0 )
      {
        started = NcaHResultToWindowsError((unsigned int)v13);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 50;
LABEL_13:
          WPP_SF_d(v14[2], v15, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, started);
          goto LABEL_27;
        }
        goto LABEL_27;
      }
      NcaFree(v11);
      v11 = lpCommandLine;
      v12 = (unsigned int)(v12 + 1);
      lpCommandLine = 0;
    }
    v16 = NcaStringBuild(&lpCommandLine, v11, L" }\"");
    if ( v16 >= 0 )
    {
      NcaFree(v11);
      v11 = lpCommandLine;
      lpCommandLine = 0;
      ExpandedCanonicalLongPathName = NcaGetExpandedCanonicalLongPathName(v17, &lpApplicationName, &v20);
      if ( ExpandedCanonicalLongPathName >= 0 )
      {
        if ( v20 )
        {
          started = NcaScriptLogsStartProcess(lpApplicationName, (LPWSTR)v11, a3, a4, a5);
        }
        else
        {
          started = 87;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 53;
            goto LABEL_13;
          }
        }
      }
      else
      {
        started = NcaHResultToWindowsError((unsigned int)ExpandedCanonicalLongPathName);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 52;
          goto LABEL_13;
        }
      }
    }
    else
    {
      started = NcaHResultToWindowsError((unsigned int)v16);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 51;
        goto LABEL_13;
      }
    }
  }
  else
  {
    started = NcaHResultToWindowsError((unsigned int)v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, started);
    v11 = lpMem;
  }
LABEL_27:
  NcaFree((LPVOID)lpApplicationName);
  NcaFree(v11);
  NcaFree(lpCommandLine);
  return started;
}

```

## disassembly

```asm
0x180009ce0  push    rbp
0x180009ce2  push    rbx
0x180009ce3  push    rsi
0x180009ce4  push    rdi
0x180009ce5  push    r12
0x180009ce7  push    r14
0x180009ce9  push    r15
0x180009ceb  mov     rbp, rsp
0x180009cee  sub     rsp, 50h
0x180009cf2  mov     r15, r8
0x180009cf5  mov     [rbp+lpMem], 0
0x180009cfd  mov     esi, edx
0x180009cff  mov     [rbp+lpCommandLine], 0
0x180009d07  mov     r12, rcx
0x180009d0a  mov     [rbp+lpApplicationName], 0
0x180009d12  xor     r8d, r8d
0x180009d15  mov     [rbp+var_20], 0
0x180009d1c  lea     rdx, aCommandGlobalF; " -Command \"& { $global:FormatEnumerati"...
0x180009d23  mov     r14, r9
0x180009d26  lea     rcx, [rbp+lpMem]
0x180009d2a  call    NcaStringBuild
0x180009d2f  test    eax, eax
0x180009d31  jns     short loc_180009D76
0x180009d33  mov     ecx, eax
0x180009d35  call    NcaHResultToWindowsError
0x180009d3a  mov     ebx, eax
0x180009d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d43  lea     rax, WPP_GLOBAL_Control
0x180009d4a  cmp     rcx, rax
0x180009d4d  jz      short loc_180009D6D
0x180009d4f  test    byte ptr [rcx+1Ch], 1
0x180009d53  jz      short loc_180009D6D
0x180009d55  mov     rcx, [rcx+10h]
0x180009d59  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x180009d60  mov     edx, 31h ; '1'
0x180009d65  mov     r9d, ebx
0x180009d68  call    WPP_SF_d
0x180009d6d  mov     rdi, [rbp+lpMem]
0x180009d71  jmp     loc_180009EEA
0x180009d76  mov     rdi, [rbp+lpMem]
0x180009d7a  xor     ebx, ebx
0x180009d7c  lea     rcx, [rbp+lpCommandLine]
0x180009d80  mov     rdx, rdi
0x180009d83  cmp     ebx, esi
0x180009d85  jnb     loc_180009E0C
0x180009d8b  lea     r8, [rbx+rbx*2]
0x180009d8f  mov     [rsp+50h+var_30], 0
0x180009d98  mov     r8, [r12+r8*8+10h]
0x180009d9d  lea     r9, aChar30; " ; [char]30 ; "
0x180009da4  call    NcaStringBuild
0x180009da9  test    eax, eax
0x180009dab  js      short loc_180009DC5
0x180009dad  mov     rcx, rdi; lpMem
0x180009db0  call    NcaFree
0x180009db5  mov     rdi, [rbp+lpCommandLine]
0x180009db9  inc     ebx
0x180009dbb  mov     [rbp+lpCommandLine], 0
0x180009dc3  jmp     short loc_180009D7C
0x180009dc5  mov     ecx, eax
0x180009dc7  call    NcaHResultToWindowsError
0x180009dcc  mov     ebx, eax
0x180009dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dd5  lea     rax, WPP_GLOBAL_Control
0x180009ddc  cmp     rcx, rax
0x180009ddf  jz      loc_180009EEA
0x180009de5  test    byte ptr [rcx+1Ch], 1
0x180009de9  jz      loc_180009EEA
0x180009def  mov     edx, 32h ; '2'
0x180009df4  mov     rcx, [rcx+10h]
0x180009df8  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x180009dff  mov     r9d, ebx
0x180009e02  call    WPP_SF_d
0x180009e07  jmp     loc_180009EEA
0x180009e0c  xor     r9d, r9d
0x180009e0f  lea     r8, asc_1800224F8; " }\""
0x180009e16  call    NcaStringBuild
0x180009e1b  test    eax, eax
0x180009e1d  jns     short loc_180009E50
0x180009e1f  mov     ecx, eax
0x180009e21  call    NcaHResultToWindowsError
0x180009e26  mov     ebx, eax
0x180009e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e2f  lea     rax, WPP_GLOBAL_Control
0x180009e36  cmp     rcx, rax
0x180009e39  jz      loc_180009EEA
0x180009e3f  test    byte ptr [rcx+1Ch], 1
0x180009e43  jz      loc_180009EEA
0x180009e49  mov     edx, 33h ; '3'
0x180009e4e  jmp     short loc_180009DF4
0x180009e50  mov     rcx, rdi; lpMem
0x180009e53  call    NcaFree
0x180009e58  mov     rdi, [rbp+lpCommandLine]
0x180009e5c  lea     r8, [rbp+var_20]
0x180009e60  lea     rdx, [rbp+lpApplicationName]
0x180009e64  mov     [rbp+lpCommandLine], 0
0x180009e6c  call    NcaGetExpandedCanonicalLongPathName
0x180009e71  test    eax, eax
0x180009e73  jns     short loc_180009EA1
0x180009e75  mov     ecx, eax
0x180009e77  call    NcaHResultToWindowsError
0x180009e7c  mov     ebx, eax
0x180009e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e85  lea     rax, WPP_GLOBAL_Control
0x180009e8c  cmp     rcx, rax
0x180009e8f  jz      short loc_180009EEA
0x180009e91  test    byte ptr [rcx+1Ch], 1
0x180009e95  jz      short loc_180009EEA
0x180009e97  mov     edx, 34h ; '4'
0x180009e9c  jmp     loc_180009DF4
0x180009ea1  cmp     [rbp+var_20], 0
0x180009ea5  jnz     short loc_180009ECD
0x180009ea7  mov     ebx, 57h ; 'W'
0x180009eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb3  lea     rax, WPP_GLOBAL_Control
0x180009eba  cmp     rcx, rax
0x180009ebd  jz      short loc_180009EEA
0x180009ebf  test    byte ptr [rcx+1Ch], 1
0x180009ec3  jz      short loc_180009EEA
0x180009ec5  lea     edx, [rbx-22h]
0x180009ec8  jmp     loc_180009DF4
0x180009ecd  mov     rax, [rbp+arg_20]
0x180009ed1  mov     r9, r14; struct NCA_PROCESS_ENVIRONMENT_ *
0x180009ed4  mov     rcx, [rbp+lpApplicationName]; lpApplicationName
0x180009ed8  mov     r8, r15; Token
0x180009edb  mov     rdx, rdi; lpCommandLine
0x180009ede  mov     [rsp+50h+var_30], rax; int *
0x180009ee3  call    ?NcaScriptLogsStartProcess@@YAKPEAG0PEAXPEAUNCA_PROCESS_ENVIRONMENT_@@PEAH@Z; NcaScriptLogsStartProcess(ushort *,ushort *,void *,NCA_PROCESS_ENVIRONMENT_ *,int *)
0x180009ee8  mov     ebx, eax
0x180009eea  mov     rcx, [rbp+lpApplicationName]; lpMem
0x180009eee  call    NcaFree
0x180009ef3  mov     rcx, rdi; lpMem
0x180009ef6  call    NcaFree
0x180009efb  mov     rcx, [rbp+lpCommandLine]; lpMem
0x180009eff  call    NcaFree
0x180009f04  mov     eax, ebx
0x180009f06  add     rsp, 50h
0x180009f0a  pop     r15
0x180009f0c  pop     r14
0x180009f0e  pop     r12
0x180009f10  pop     rdi
0x180009f11  pop     rsi
0x180009f12  pop     rbx
0x180009f13  pop     rbp
0x180009f14  retn
```
