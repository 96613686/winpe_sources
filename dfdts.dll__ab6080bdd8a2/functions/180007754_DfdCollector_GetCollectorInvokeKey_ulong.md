# DfdCollector::GetCollectorInvokeKey(ulong *)

- ea: `0x180007754`
- end: `0x18000796a`
- name: `?GetCollectorInvokeKey@DfdCollector@@AEAAXPEAK@Z`
- size: `534`
- prototype: `void __fastcall(DfdCollector *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002450`

## callees

- `0x180003984`
- `0x180005178`
- `0x180007754`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180007837`
- `ADVAPI32!RegSetValueExW` at `0x1800078d5`
- `ADVAPI32!RegSetValueExW` at `0x180007921`
- `ADVAPI32!RegSetValueExW` at `0x180007837`
- `ADVAPI32!RegSetValueExW` at `0x1800078d5`
- `ADVAPI32!RegSetValueExW` at `0x180007921`
- `ADVAPI32!RegCreateKeyExW` at `0x1800077c5`
- `ADVAPI32!RegCreateKeyExW` at `0x1800077c5`
- `ADVAPI32!RegCloseKey` at `0x18000795c`
- `ADVAPI32!RegCloseKey` at `0x18000795c`
- `ADVAPI32!RegQueryValueExW` at `0x1800078a8`
- `ADVAPI32!RegQueryValueExW` at `0x1800078a8`

## pseudocode

```c
void __fastcall DfdCollector::GetCollectorInvokeKey(DfdCollector *this, unsigned int *a2)
{
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD Type; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+80h] [rbp+20h] BYREF
  int v10; // [rsp+84h] [rbp+24h]
  DWORD v11; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  Data = 0;
  hKey = 0;
  Type = 4;
  cbData = 4;
  v11 = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         &v11);
  if ( !v3 )
  {
    if ( v11 == 1 )
    {
      v4 = RegSetValueExW(hKey, L"DFDCollectorInvokeTimes", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v4 )
        goto LABEL_22;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v6 = 14;
    }
    else
    {
      Data = 0;
      v4 = RegQueryValueExW(hKey, L"DFDCollectorInvokeTimes", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v4 )
      {
        if ( v4 == 2 )
        {
          RegSetValueExW(hKey, L"DFDCollectorInvokeTimes", 0, 4u, (const BYTE *)&Data, 4u);
          goto LABEL_22;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v6 = 15;
      }
      else
      {
        ++Data;
        v4 = RegSetValueExW(hKey, L"DFDCollectorInvokeTimes", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v4 )
        {
          *a2 = Data;
          goto LABEL_22;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v6 = 16;
      }
    }
    WPP_SF_DD(v5[2], v6, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids, Data, v4);
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics",
      v3);
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180007754  mov     r11, rsp
0x180007757  mov     [r11+8], rcx
0x18000775b  push    rbp
0x18000775c  push    rbx
0x18000775d  push    rdi
0x18000775e  mov     rbp, rsp
0x180007761  sub     rsp, 60h
0x180007765  lea     rax, [rbp+arg_10]
0x180007769  mov     [rbp+Data], 0
0x180007770  mov     [r11-38h], rax
0x180007774  mov     rbx, rdx
0x180007777  lea     rax, [rbp+hKey]
0x18000777b  mov     [rbp+hKey], 0
0x180007783  mov     [r11-40h], rax
0x180007787  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000778e  mov     qword ptr [r11-48h], 0
0x180007796  mov     edi, 4
0x18000779b  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800077a3  xor     r9d, r9d; lpClass
0x1800077a6  xor     r8d, r8d; Reserved
0x1800077a9  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800077b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800077b8  mov     [rbp+Type], edi
0x1800077bb  mov     [rbp+cbData], edi
0x1800077be  mov     [rbp+arg_10], 0
0x1800077c5  call    cs:__imp_RegCreateKeyExW
0x1800077cb  test    eax, eax
0x1800077cd  jz      short loc_180007813
0x1800077cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077d6  lea     rdx, WPP_GLOBAL_Control
0x1800077dd  cmp     rcx, rdx
0x1800077e0  jz      loc_180007953
0x1800077e6  test    byte ptr [rcx+1Ch], 1
0x1800077ea  jz      loc_180007953
0x1800077f0  mov     rcx, [rcx+10h]
0x1800077f4  lea     edx, [rdi+9]
0x1800077f7  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800077fe  mov     [rsp+60h+dwOptions], eax
0x180007802  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007809  call    WPP_SF_Sd
0x18000780e  jmp     loc_180007953
0x180007813  cmp     [rbp+arg_10], 1
0x180007817  lea     rdx, aDfdcollectorin; "DFDCollectorInvokeTimes"
0x18000781e  mov     rcx, [rbp+hKey]; hKey
0x180007822  jnz     short loc_180007888
0x180007824  lea     rax, [rbp+Data]
0x180007828  mov     [rsp+60h+samDesired], edi; cbData
0x18000782c  mov     r9d, edi; dwType
0x18000782f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180007834  xor     r8d, r8d; Reserved
0x180007837  call    cs:__imp_RegSetValueExW
0x18000783d  test    eax, eax
0x18000783f  jz      loc_180007953
0x180007845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784c  lea     rdx, WPP_GLOBAL_Control
0x180007853  cmp     rcx, rdx
0x180007856  jz      loc_180007953
0x18000785c  test    byte ptr [rcx+1Ch], 1
0x180007860  jz      loc_180007953
0x180007866  mov     edx, 0Eh
0x18000786b  mov     r9d, [rbp+Data]
0x18000786f  lea     r8, WPP_7cd7c10ab54f3ad41c442ebb2d0f47f1_Traceguids
0x180007876  mov     rcx, [rcx+10h]
0x18000787a  mov     [rsp+60h+dwOptions], eax
0x18000787e  call    WPP_SF_DD
0x180007883  jmp     loc_180007953
0x180007888  lea     rax, [rbp+cbData]
0x18000788c  mov     [rbp+Data], 0
0x180007893  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180007898  lea     r9, [rbp+Type]; lpType
0x18000789c  lea     rax, [rbp+Data]
0x1800078a0  xor     r8d, r8d; lpReserved
0x1800078a3  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800078a8  call    cs:__imp_RegQueryValueExW
0x1800078ae  test    eax, eax
0x1800078b0  jz      short loc_180007900
0x1800078b2  cmp     eax, 2
0x1800078b5  jnz     short loc_1800078DD
0x1800078b7  mov     rcx, [rbp+hKey]; hKey
0x1800078bb  lea     rax, [rbp+Data]
0x1800078bf  mov     [rsp+60h+samDesired], edi; cbData
0x1800078c3  lea     rdx, aDfdcollectorin; "DFDCollectorInvokeTimes"
0x1800078ca  mov     r9d, edi; dwType
0x1800078cd  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800078d2  xor     r8d, r8d; Reserved
0x1800078d5  call    cs:__imp_RegSetValueExW
0x1800078db  jmp     short loc_180007953
0x1800078dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e4  lea     rdx, WPP_GLOBAL_Control
0x1800078eb  cmp     rcx, rdx
0x1800078ee  jz      short loc_180007953
0x1800078f0  test    byte ptr [rcx+1Ch], 1
0x1800078f4  jz      short loc_180007953
0x1800078f6  mov     edx, 0Fh
0x1800078fb  jmp     loc_18000786B
0x180007900  mov     rcx, [rbp+hKey]; hKey
0x180007904  lea     rax, [rbp+Data]
0x180007908  inc     [rbp+Data]
0x18000790b  lea     rdx, aDfdcollectorin; "DFDCollectorInvokeTimes"
0x180007912  mov     [rsp+60h+samDesired], edi; cbData
0x180007916  mov     r9d, edi; dwType
0x180007919  xor     r8d, r8d; Reserved
0x18000791c  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180007921  call    cs:__imp_RegSetValueExW
0x180007927  test    eax, eax
0x180007929  jz      short loc_18000794E
0x18000792b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007932  lea     rdx, WPP_GLOBAL_Control
0x180007939  cmp     rcx, rdx
0x18000793c  jz      short loc_180007953
0x18000793e  test    byte ptr [rcx+1Ch], 1
0x180007942  jz      short loc_180007953
0x180007944  mov     edx, 10h
0x180007949  jmp     loc_18000786B
0x18000794e  mov     eax, [rbp+Data]
0x180007951  mov     [rbx], eax
0x180007953  mov     rcx, [rbp+hKey]; hKey
0x180007957  test    rcx, rcx
0x18000795a  jz      short loc_180007962
0x18000795c  call    cs:__imp_RegCloseKey
0x180007962  add     rsp, 60h
0x180007966  pop     rdi
0x180007967  pop     rbx
0x180007968  pop     rbp
0x180007969  retn
```
