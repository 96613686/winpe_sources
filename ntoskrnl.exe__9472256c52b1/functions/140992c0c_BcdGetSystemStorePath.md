# BcdGetSystemStorePath

- ea: `0x140992c0c`
- end: `0x140992e2d`
- name: `BcdGetSystemStorePath`
- size: `545`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14098eb74`

## callees

- `0x14054a9f0`
- `0x14054aa90`
- `0x14072d684`
- `0x140992c0c`
- `0x1409935a8`
- `0x140993780`
- `0x140a92ae0`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140992ddb`: `Failed to get system store path. Status: %x`
- `0x140992c61`: `System store path: %s`
- `0x140992d54`: `Using cached BCD path: %s`
- `0x140992d3f`: `system32\config\BootBCD`

## pseudocode

```c
__int64 __fastcall BcdGetSystemStorePath(wchar_t **a1)
{
  wchar_t *v2; // rsi
  __int64 FirmwareType; // rdx
  __int64 v4; // rcx
  int v5; // edx
  const wchar_t *v6; // rbp
  int SystemPartition; // eax
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r14d
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  char IsStateSeparationEnabled; // al
  const wchar_t *v15; // rbp
  rsize_t v16; // rbx
  wchar_t *Pool2; // rax
  PVOID P; // [rsp+58h] [rbp+10h] BYREF
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v20 = 0;
  v2 = 0;
  P = 0;
  FirmwareType = (unsigned int)BiGetFirmwareType(&v20);
  if ( (v20 & 0x10000) != 0 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v4, FirmwareType);
    v15 = L"\\OSDataRoot\\Windows\\";
    if ( !IsStateSeparationEnabled )
      v15 = L"\\SystemRoot\\";
    v16 = IsStateSeparationEnabled != 0 ? 44LL : 36LL;
    Pool2 = (wchar_t *)ExAllocatePool2(258, 2 * v16, 1262764866);
    v13 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741801;
    wcscpy_s(Pool2, v16, v15);
    wcscat_s(v13, v16, L"system32\\config\\BootBCD");
    BiLogMessage(2, L"Using cached BCD path: %s", v13);
    v8 = 0;
    goto LABEL_14;
  }
  v5 = FirmwareType - 1;
  if ( v5 )
  {
    if ( (unsigned int)(v5 - 1) >= 2 )
    {
      v8 = -1073741637;
      BiLogMessage(4, L"Failed to get system store path. Status: %x", 3221225659LL);
      return (unsigned int)v8;
    }
    v6 = L"\\EFI\\Microsoft\\Boot\\BCD";
  }
  else
  {
    v6 = L"\\Boot\\BCD";
  }
  BiLogMessage(2, L"System store path: %s", v6);
  SystemPartition = BiGetSystemPartition(&P);
  v8 = SystemPartition;
  if ( SystemPartition < 0 )
  {
    v13 = 0;
    BiLogMessage(4, L"Failed to get system partition. Status: %x", (unsigned int)SystemPartition);
    v2 = (wchar_t *)P;
    goto LABEL_15;
  }
  v2 = (wchar_t *)P;
  BiLogMessage(2, L"System partition: %s", P);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v6[v10] );
  do
    ++v9;
  while ( v2[v9] );
  v11 = v10 + v9 + 1;
  v12 = (wchar_t *)ExAllocatePool2(258, 2LL * v11, 1262764866);
  v13 = v12;
  if ( v12 )
  {
    wcscpy_s(v12, v11, v2);
    wcscat_s(v13, v11, v6);
LABEL_14:
    *a1 = v13;
    goto LABEL_15;
  }
  v8 = -1073741801;
LABEL_15:
  if ( v2 )
    ExFreePoolWithTag(v2, 0x4B444342u);
  if ( v8 < 0 && v13 )
    ExFreePoolWithTag(v13, 0x4B444342u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140992c0c  mov     rax, rsp
0x140992c0f  mov     [rax+8], rbx
0x140992c13  mov     [rax+20h], rbp
0x140992c17  push    rsi
0x140992c18  push    rdi
0x140992c19  push    r12
0x140992c1b  push    r14
0x140992c1d  push    r15
0x140992c1f  sub     rsp, 20h
0x140992c23  xor     r12d, r12d
0x140992c26  mov     r15, rcx
0x140992c29  lea     rcx, [rax+18h]
0x140992c2d  mov     [rax+18h], r12
0x140992c31  mov     esi, r12d
0x140992c34  mov     [rax+10h], r12
0x140992c38  call    BiGetFirmwareType
0x140992c3d  test    [rsp+48h+arg_10], 10000h
0x140992c46  mov     edx, eax
0x140992c48  jnz     loc_140992CEC
0x140992c4e  sub     edx, 1
0x140992c51  jnz     loc_140992DC4
0x140992c57  lea     rbp, aBootBcd; "\\Boot\\BCD"
0x140992c5e  mov     r8, rbp
0x140992c61  lea     rdx, aSystemStorePat; "System store path: %s"
0x140992c68  mov     ecx, 2
0x140992c6d  call    BiLogMessage
0x140992c72  lea     rcx, [rsp+48h+P]
0x140992c77  call    BiGetSystemPartition
0x140992c7c  mov     ebx, eax
0x140992c7e  test    eax, eax
0x140992c80  js      loc_140992DF1
0x140992c86  mov     rsi, [rsp+48h+P]
0x140992c8b  lea     rdx, aSystemPartitio_1; "System partition: %s"
0x140992c92  mov     r8, rsi
0x140992c95  mov     ecx, 2
0x140992c9a  call    BiLogMessage
0x140992c9f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140992ca3  mov     rcx, rax
0x140992ca6  inc     rcx
0x140992ca9  cmp     [rbp+rcx*2+0], r12w
0x140992caf  jnz     short loc_140992CA6
0x140992cb1  inc     rax
0x140992cb4  cmp     [rsi+rax*2], r12w
0x140992cb9  jnz     short loc_140992CB1
0x140992cbb  lea     r14, [rax+1]
0x140992cbf  mov     r8d, 4B444342h
0x140992cc5  add     r14, rcx
0x140992cc8  mov     ecx, 102h
0x140992ccd  mov     r14d, r14d
0x140992cd0  lea     rdx, [r14+r14]
0x140992cd4  call    ExAllocatePool2
0x140992cd9  mov     rdi, rax
0x140992cdc  test    rax, rax
0x140992cdf  jnz     loc_140992D9F
0x140992ce5  mov     ebx, 0C0000017h
0x140992cea  jmp     short loc_140992D6B
0x140992cec  call    RtlIsStateSeparationEnabled
0x140992cf1  test    al, al
0x140992cf3  lea     rcx, aSystemroot_3; "\\SystemRoot\\"
0x140992cfa  lea     rbp, aOsdatarootWind_2; "\\OSDataRoot\\Windows\\"
0x140992d01  mov     r8d, 4B444342h
0x140992d07  cmovz   rbp, rcx
0x140992d0b  neg     al
0x140992d0d  mov     ecx, 102h
0x140992d12  sbb     rbx, rbx
0x140992d15  and     ebx, 8
0x140992d18  add     rbx, 24h ; '$'
0x140992d1c  lea     rdx, [rbx+rbx]
0x140992d20  call    ExAllocatePool2
0x140992d25  mov     rdi, rax
0x140992d28  test    rax, rax
0x140992d2b  jz      loc_140992DBD
0x140992d31  mov     r8, rbp; Src
0x140992d34  mov     rdx, rbx; SizeInWords
0x140992d37  mov     rcx, rax; Dst
0x140992d3a  call    wcscpy_s
0x140992d3f  lea     r8, aSystem32Config_7; "system32\\config\\BootBCD"
0x140992d46  mov     rdx, rbx; SizeInWords
0x140992d49  mov     rcx, rdi; Dst
0x140992d4c  call    wcscat_s
0x140992d51  mov     r8, rdi
0x140992d54  lea     rdx, aUsingCachedBcd; "Using cached BCD path: %s"
0x140992d5b  mov     ecx, 2
0x140992d60  call    BiLogMessage
0x140992d65  mov     ebx, r12d
0x140992d68  mov     [r15], rdi
0x140992d6b  test    rsi, rsi
0x140992d6e  jz      short loc_140992D7D
0x140992d70  mov     edx, 4B444342h; Tag
0x140992d75  mov     rcx, rsi; P
0x140992d78  call    ExFreePoolWithTag
0x140992d7d  test    ebx, ebx
0x140992d7f  js      loc_140992E12
0x140992d85  mov     rbp, [rsp+48h+arg_18]
0x140992d8a  mov     eax, ebx
0x140992d8c  mov     rbx, [rsp+48h+arg_0]
0x140992d91  add     rsp, 20h
0x140992d95  pop     r15
0x140992d97  pop     r14
0x140992d99  pop     r12
0x140992d9b  pop     rdi
0x140992d9c  pop     rsi
0x140992d9d  retn
0x140992d9f  mov     r8, rsi; Src
0x140992da2  mov     rdx, r14; SizeInWords
0x140992da5  mov     rcx, rdi; Dst
0x140992da8  call    wcscpy_s
0x140992dad  mov     r8, rbp; Src
0x140992db0  mov     rdx, r14; SizeInWords
0x140992db3  mov     rcx, rdi; Dst
0x140992db6  call    wcscat_s
0x140992dbb  jmp     short loc_140992D68
0x140992dbd  mov     ebx, 0C0000017h
0x140992dc2  jmp     short loc_140992D85
0x140992dc4  sub     edx, 1
0x140992dc7  jz      loc_140B63510
0x140992dcd  cmp     edx, 1
0x140992dd0  jz      loc_140B63510
0x140992dd6  mov     ebx, 0C00000BBh
0x140992ddb  lea     rdx, aFailedToGetSys_0; "Failed to get system store path. Status"...
0x140992de2  mov     r8d, ebx
0x140992de5  mov     ecx, 4
0x140992dea  call    BiLogMessage
0x140992def  jmp     short loc_140992D85
0x140992df1  mov     r8d, eax
0x140992df4  lea     rdx, aFailedToGetSys; "Failed to get system partition. Status:"...
0x140992dfb  mov     ecx, 4
0x140992e00  mov     rdi, r12
0x140992e03  call    BiLogMessage
0x140992e08  mov     rsi, [rsp+48h+P]
0x140992e0d  jmp     loc_140992D6B
0x140992e12  test    rdi, rdi
0x140992e15  jz      loc_140992D85
0x140992e1b  mov     edx, 4B444342h; Tag
0x140992e20  mov     rcx, rdi; P
0x140992e23  call    ExFreePoolWithTag
0x140992e28  jmp     loc_140992D85
0x140b63510  lea     rbp, aEfiMicrosoftBo; "\\EFI\\Microsoft\\Boot\\BCD"
0x140b63517  jmp     loc_140992C5E
```
