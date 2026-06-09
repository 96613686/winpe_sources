# GetLegacyProviderEntryPoints

- ea: `0x1400034bc`
- end: `0x140003808`
- name: `GetLegacyProviderEntryPoints`
- size: `844`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003d5c`

## callees

- `0x1400034bc`
- `0x140004b30`
- `0x140004b58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003543`
- `KERNEL32!GetLastError` at `0x140003593`
- `KERNEL32!GetLastError` at `0x1400035e3`
- `KERNEL32!GetLastError` at `0x140003633`
- `KERNEL32!GetLastError` at `0x140003683`
- `KERNEL32!GetLastError` at `0x1400036c7`
- `KERNEL32!GetLastError` at `0x140003708`
- `KERNEL32!GetLastError` at `0x140003543`
- `KERNEL32!GetLastError` at `0x140003593`
- `KERNEL32!GetLastError` at `0x1400035e3`
- `KERNEL32!GetLastError` at `0x140003633`
- `KERNEL32!GetLastError` at `0x140003683`
- `KERNEL32!GetLastError` at `0x1400036c7`
- `KERNEL32!GetLastError` at `0x140003708`
- `KERNEL32!GetProcAddress` at `0x14000350d`
- `KERNEL32!GetProcAddress` at `0x14000355d`
- `KERNEL32!GetProcAddress` at `0x1400035ad`
- `KERNEL32!GetProcAddress` at `0x1400035fd`
- `KERNEL32!GetProcAddress` at `0x14000364d`
- `KERNEL32!GetProcAddress` at `0x14000369d`
- `KERNEL32!GetProcAddress` at `0x1400036de`
- `KERNEL32!GetProcAddress` at `0x14000373a`
- `KERNEL32!GetProcAddress` at `0x14000377d`
- `KERNEL32!GetProcAddress` at `0x1400037c0`
- `KERNEL32!GetProcAddress` at `0x14000350d`
- `KERNEL32!GetProcAddress` at `0x14000355d`
- `KERNEL32!GetProcAddress` at `0x1400035ad`
- `KERNEL32!GetProcAddress` at `0x1400035fd`
- `KERNEL32!GetProcAddress` at `0x14000364d`
- `KERNEL32!GetProcAddress` at `0x14000369d`
- `KERNEL32!GetProcAddress` at `0x1400036de`
- `KERNEL32!GetProcAddress` at `0x14000373a`
- `KERNEL32!GetProcAddress` at `0x14000377d`
- `KERNEL32!GetProcAddress` at `0x1400037c0`

## string_xrefs

- `0x140003773`: `FaxExtInitializeConfig`

## pseudocode

```c
__int64 __fastcall GetLegacyProviderEntryPoints(HMODULE hModule, _QWORD *a2)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  FARPROC v7; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  ProcAddress = GetProcAddress(hModule, "FaxDevInitialize");
  a2[270] = ProcAddress;
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 39;
LABEL_40:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_200271385d87382553faba38592a1280_Traceguids, LastError);
    return 0;
  }
  v7 = GetProcAddress(hModule, "FaxDevStartJob");
  a2[271] = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 40;
    goto LABEL_40;
  }
  v8 = GetProcAddress(hModule, "FaxDevEndJob");
  a2[272] = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 41;
    goto LABEL_40;
  }
  v9 = GetProcAddress(hModule, "FaxDevSend");
  a2[273] = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 42;
    goto LABEL_40;
  }
  v10 = GetProcAddress(hModule, "FaxDevReceive");
  a2[274] = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 43;
    goto LABEL_40;
  }
  v11 = GetProcAddress(hModule, "FaxDevReportStatus");
  a2[275] = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 44;
    goto LABEL_40;
  }
  v12 = GetProcAddress(hModule, "FaxDevAbortOperation");
  a2[276] = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LastError = GetLastError();
    v6 = 45;
    goto LABEL_40;
  }
  v14 = GetProcAddress(hModule, "FaxDevVirtualDeviceCreation");
  a2[278] = v14;
  if ( !v14
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  v15 = GetProcAddress(hModule, "FaxExtInitializeConfig");
  a2[280] = v15;
  if ( !v15
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  v16 = GetProcAddress(hModule, "FaxDevShutdown");
  a2[279] = v16;
  if ( !v16
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_200271385d87382553faba38592a1280_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x1400034bc  push    rbx
0x1400034be  push    rbp
0x1400034bf  push    rdi
0x1400034c0  push    r14
0x1400034c2  sub     rsp, 28h
0x1400034c6  mov     rbx, rdx
0x1400034c9  mov     rdi, rcx
0x1400034cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034d3  lea     rbp, WPP_GLOBAL_Control
0x1400034da  lea     r14, WPP_200271385d87382553faba38592a1280_Traceguids
0x1400034e1  cmp     rcx, rbp
0x1400034e4  jz      short loc_140003503
0x1400034e6  test    byte ptr [rcx+1Ch], 4
0x1400034ea  jz      short loc_140003503
0x1400034ec  cmp     byte ptr [rcx+19h], 5
0x1400034f0  jb      short loc_140003503
0x1400034f2  mov     rcx, [rcx+10h]
0x1400034f6  mov     edx, 26h ; '&'
0x1400034fb  mov     r8, r14
0x1400034fe  call    WPP_SF_
0x140003503  lea     rdx, ProcName; "FaxDevInitialize"
0x14000350a  mov     rcx, rdi; hModule
0x14000350d  call    cs:__imp_GetProcAddress
0x140003513  mov     [rbx+870h], rax
0x14000351a  test    rax, rax
0x14000351d  jnz     short loc_140003553
0x14000351f  mov     rax, cs:WPP_GLOBAL_Control
0x140003526  cmp     rax, rbp
0x140003529  jz      loc_140003729
0x14000352f  test    byte ptr [rax+1Ch], 4
0x140003533  jz      loc_140003729
0x140003539  cmp     byte ptr [rax+19h], 2
0x14000353d  jb      loc_140003729
0x140003543  call    cs:__imp_GetLastError
0x140003549  mov     edx, 27h ; '''
0x14000354e  jmp     loc_140003713
0x140003553  lea     rdx, aFaxdevstartjob; "FaxDevStartJob"
0x14000355a  mov     rcx, rdi; hModule
0x14000355d  call    cs:__imp_GetProcAddress
0x140003563  mov     [rbx+878h], rax
0x14000356a  test    rax, rax
0x14000356d  jnz     short loc_1400035A3
0x14000356f  mov     rax, cs:WPP_GLOBAL_Control
0x140003576  cmp     rax, rbp
0x140003579  jz      loc_140003729
0x14000357f  test    byte ptr [rax+1Ch], 4
0x140003583  jz      loc_140003729
0x140003589  cmp     byte ptr [rax+19h], 2
0x14000358d  jb      loc_140003729
0x140003593  call    cs:__imp_GetLastError
0x140003599  mov     edx, 28h ; '('
0x14000359e  jmp     loc_140003713
0x1400035a3  lea     rdx, aFaxdevendjob; "FaxDevEndJob"
0x1400035aa  mov     rcx, rdi; hModule
0x1400035ad  call    cs:__imp_GetProcAddress
0x1400035b3  mov     [rbx+880h], rax
0x1400035ba  test    rax, rax
0x1400035bd  jnz     short loc_1400035F3
0x1400035bf  mov     rax, cs:WPP_GLOBAL_Control
0x1400035c6  cmp     rax, rbp
0x1400035c9  jz      loc_140003729
0x1400035cf  test    byte ptr [rax+1Ch], 4
0x1400035d3  jz      loc_140003729
0x1400035d9  cmp     byte ptr [rax+19h], 2
0x1400035dd  jb      loc_140003729
0x1400035e3  call    cs:__imp_GetLastError
0x1400035e9  mov     edx, 29h ; ')'
0x1400035ee  jmp     loc_140003713
0x1400035f3  lea     rdx, aFaxdevsend; "FaxDevSend"
0x1400035fa  mov     rcx, rdi; hModule
0x1400035fd  call    cs:__imp_GetProcAddress
0x140003603  mov     [rbx+888h], rax
0x14000360a  test    rax, rax
0x14000360d  jnz     short loc_140003643
0x14000360f  mov     rax, cs:WPP_GLOBAL_Control
0x140003616  cmp     rax, rbp
0x140003619  jz      loc_140003729
0x14000361f  test    byte ptr [rax+1Ch], 4
0x140003623  jz      loc_140003729
0x140003629  cmp     byte ptr [rax+19h], 2
0x14000362d  jb      loc_140003729
0x140003633  call    cs:__imp_GetLastError
0x140003639  mov     edx, 2Ah ; '*'
0x14000363e  jmp     loc_140003713
0x140003643  lea     rdx, aFaxdevreceive; "FaxDevReceive"
0x14000364a  mov     rcx, rdi; hModule
0x14000364d  call    cs:__imp_GetProcAddress
0x140003653  mov     [rbx+890h], rax
0x14000365a  test    rax, rax
0x14000365d  jnz     short loc_140003693
0x14000365f  mov     rax, cs:WPP_GLOBAL_Control
0x140003666  cmp     rax, rbp
0x140003669  jz      loc_140003729
0x14000366f  test    byte ptr [rax+1Ch], 4
0x140003673  jz      loc_140003729
0x140003679  cmp     byte ptr [rax+19h], 2
0x14000367d  jb      loc_140003729
0x140003683  call    cs:__imp_GetLastError
0x140003689  mov     edx, 2Bh ; '+'
0x14000368e  jmp     loc_140003713
0x140003693  lea     rdx, aFaxdevreportst; "FaxDevReportStatus"
0x14000369a  mov     rcx, rdi; hModule
0x14000369d  call    cs:__imp_GetProcAddress
0x1400036a3  mov     [rbx+898h], rax
0x1400036aa  test    rax, rax
0x1400036ad  jnz     short loc_1400036D4
0x1400036af  mov     rax, cs:WPP_GLOBAL_Control
0x1400036b6  cmp     rax, rbp
0x1400036b9  jz      short loc_140003729
0x1400036bb  test    byte ptr [rax+1Ch], 4
0x1400036bf  jz      short loc_140003729
0x1400036c1  cmp     byte ptr [rax+19h], 2
0x1400036c5  jb      short loc_140003729
0x1400036c7  call    cs:__imp_GetLastError
0x1400036cd  mov     edx, 2Ch ; ','
0x1400036d2  jmp     short loc_140003713
0x1400036d4  lea     rdx, aFaxdevabortope; "FaxDevAbortOperation"
0x1400036db  mov     rcx, rdi; hModule
0x1400036de  call    cs:__imp_GetProcAddress
0x1400036e4  mov     [rbx+8A0h], rax
0x1400036eb  test    rax, rax
0x1400036ee  jnz     short loc_140003730
0x1400036f0  mov     rax, cs:WPP_GLOBAL_Control
0x1400036f7  cmp     rax, rbp
0x1400036fa  jz      short loc_140003729
0x1400036fc  test    byte ptr [rax+1Ch], 4
0x140003700  jz      short loc_140003729
0x140003702  cmp     byte ptr [rax+19h], 2
0x140003706  jb      short loc_140003729
0x140003708  call    cs:__imp_GetLastError
0x14000370e  mov     edx, 2Dh ; '-'
0x140003713  mov     rcx, cs:WPP_GLOBAL_Control
0x14000371a  mov     r9d, eax
0x14000371d  mov     r8, r14
0x140003720  mov     rcx, [rcx+10h]
0x140003724  call    WPP_SF_d
0x140003729  xor     eax, eax
0x14000372b  jmp     loc_1400037FE
0x140003730  lea     rdx, aFaxdevvirtuald; "FaxDevVirtualDeviceCreation"
0x140003737  mov     rcx, rdi; hModule
0x14000373a  call    cs:__imp_GetProcAddress
0x140003740  mov     [rbx+8B0h], rax
0x140003747  test    rax, rax
0x14000374a  jnz     short loc_140003773
0x14000374c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003753  cmp     rcx, rbp
0x140003756  jz      short loc_140003773
0x140003758  test    byte ptr [rcx+1Ch], 4
0x14000375c  jz      short loc_140003773
0x14000375e  cmp     byte ptr [rcx+19h], 5
0x140003762  jb      short loc_140003773
0x140003764  mov     rcx, [rcx+10h]
0x140003768  lea     edx, [rax+2Eh]
0x14000376b  mov     r8, r14
0x14000376e  call    WPP_SF_
0x140003773  lea     rdx, aFaxextinitiali; "FaxExtInitializeConfig"
0x14000377a  mov     rcx, rdi; hModule
0x14000377d  call    cs:__imp_GetProcAddress
0x140003783  mov     [rbx+8C0h], rax
0x14000378a  test    rax, rax
0x14000378d  jnz     short loc_1400037B6
0x14000378f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003796  cmp     rcx, rbp
0x140003799  jz      short loc_1400037B6
0x14000379b  test    byte ptr [rcx+1Ch], 4
0x14000379f  jz      short loc_1400037B6
0x1400037a1  cmp     byte ptr [rcx+19h], 5
0x1400037a5  jb      short loc_1400037B6
0x1400037a7  mov     rcx, [rcx+10h]
0x1400037ab  lea     edx, [rax+2Fh]
0x1400037ae  mov     r8, r14
0x1400037b1  call    WPP_SF_
0x1400037b6  lea     rdx, aFaxdevshutdown; "FaxDevShutdown"
0x1400037bd  mov     rcx, rdi; hModule
0x1400037c0  call    cs:__imp_GetProcAddress
0x1400037c6  mov     [rbx+8B8h], rax
0x1400037cd  test    rax, rax
0x1400037d0  jnz     short loc_1400037F9
0x1400037d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037d9  cmp     rcx, rbp
0x1400037dc  jz      short loc_1400037F9
0x1400037de  test    byte ptr [rcx+1Ch], 4
0x1400037e2  jz      short loc_1400037F9
0x1400037e4  cmp     byte ptr [rcx+19h], 5
0x1400037e8  jb      short loc_1400037F9
0x1400037ea  mov     rcx, [rcx+10h]
0x1400037ee  lea     edx, [rax+30h]
0x1400037f1  mov     r8, r14
0x1400037f4  call    WPP_SF_
0x1400037f9  mov     eax, 1
0x1400037fe  add     rsp, 28h
0x140003802  pop     r14
0x140003804  pop     rdi
0x140003805  pop     rbp
0x140003806  pop     rbx
0x140003807  retn
```
