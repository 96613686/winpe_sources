# DsRolepAddValuesToNullSessionPipes

- ea: `0x18001e7bc`
- end: `0x18001eaa1`
- name: `DsRolepAddValuesToNullSessionPipes`
- size: `741`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x1800150a8`
- `0x18001e7bc`
- `0x18002c012`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e92d`
- `msvcrt!_wcsicmp` at `0x18001e92d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e89d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e89d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e7fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e7fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ea53`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ea53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea7e`
- `ntdll!RtlAllocateHeap` at `0x18001e865`
- `ntdll!RtlAllocateHeap` at `0x18001e865`
- `ntdll!RtlFreeHeap` at `0x18001ea6d`
- `ntdll!RtlFreeHeap` at `0x18001ea6d`

## string_xrefs

- `0x18001e7ec`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 __fastcall DsRolepAddValuesToNullSessionPipes(char a1)
{
  unsigned int ValueW; // ebx
  char *pvData; // rsi
  unsigned __int64 v4; // rdi
  _QWORD *v5; // rdx
  char *v6; // r13
  DWORD v7; // ecx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rax
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  bool v15; // cf
  _QWORD *v16; // r12
  unsigned __int64 v17; // r15
  __int64 v18; // r14
  __int64 v19; // r8
  __int64 v20; // rax
  HKEY hkey; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v23; // [rsp+48h] [rbp-38h]
  _QWORD v24[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-20h] BYREF
  ULONG pulResult; // [rsp+C8h] [rbp+48h] BYREF
  DWORD pcbData; // [rsp+D0h] [rbp+50h] BYREF
  DWORD v28; // [rsp+D8h] [rbp+58h]

  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
             0,
             3u,
             &hkey);
  if ( !ValueW )
  {
    pcbData = 0;
    ValueW = RegGetValueW(hkey, 0, L"NullSessionPipes", 0x20u, 0, 0, &pcbData);
    if ( !ValueW )
    {
      v28 = pcbData + 80;
      pvData = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, pcbData + 80 + pcbData);
      if ( pvData )
      {
        v4 = pcbData;
        ValueW = RegGetValueW(hkey, 0, L"NullSessionPipes", 0x20u, 0, pvData, &pcbData);
        if ( !ValueW )
        {
          v25[0] = L"netlogon";
          v24[0] = L"netlogon";
          v25[2] = L"lsarpc";
          v5 = v25;
          v25[1] = L"samr";
          LOWORD(pulResult) = 0;
          v6 = &pvData[2 * (v4 >> 1)];
          BYTE2(pulResult) = 0;
          v24[1] = L"samr";
          v7 = pcbData;
          if ( a1 )
            v5 = v24;
          v23 = v5;
          v8 = 0;
          if ( (unsigned __int64)pcbData >> 1 != 1 )
          {
            do
            {
              v9 = 0;
              v10 = 2 * v8;
              while ( v9 < 3 - (unsigned __int64)(a1 != 0) )
              {
                v11 = _wcsicmp((const wchar_t *)&pvData[v10], (const wchar_t *)v5[v9]);
                v5 = v23;
                if ( !v11 )
                {
                  *((_BYTE *)&pulResult + v9) = 1;
                  break;
                }
                ++v9;
              }
              v12 = -1;
              do
                ++v12;
              while ( *(_WORD *)&pvData[2 * v12 + v10] );
              v7 = pcbData;
              v8 += v12 + 1;
            }
            while ( v8 < ((unsigned __int64)pcbData >> 1) - 1 );
          }
          memcpy_0(v6, pvData, v7);
          v13 = 0;
          v14 = ((unsigned __int64)pcbData >> 1) - 1;
          v15 = a1 != 0;
          v16 = v23;
          v17 = 3LL - v15;
          while ( v13 < v17 )
          {
            if ( !*((_BYTE *)&pulResult + v13) )
            {
              v18 = v16[v13];
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)(v18 + 2 * v19) );
              if ( v19 + v14 + 2 >= (unsigned __int64)v28 >> 1 )
              {
                ValueW = 31;
                goto LABEL_30;
              }
              memcpy_0(&v6[2 * v14], (const void *)v16[v13], 2 * v19 + 2);
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)(v18 + 2 * v20) );
              v14 += v20 + 1;
            }
            ++v13;
          }
          *(_WORD *)&v6[2 * v14] = 0;
          pulResult = 0;
          if ( ULongLongToULong(2 * v14 + 2, &pulResult) )
            ValueW = 534;
          else
            ValueW = RegSetValueExW(hkey, L"NullSessionPipes", 0, 7u, (const BYTE *)v6, pulResult);
        }
LABEL_30:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvData);
      }
      else
      {
        ValueW = 8;
      }
    }
    RegCloseKey(hkey);
  }
  return ValueW;
}

```

## disassembly

```asm
0x18001e7bc  mov     [rsp-38h+arg_0], rbx
0x18001e7c1  push    rbp
0x18001e7c2  push    rsi
0x18001e7c3  push    rdi
0x18001e7c4  push    r12
0x18001e7c6  push    r13
0x18001e7c8  push    r14
0x18001e7ca  push    r15
0x18001e7cc  mov     rbp, rsp
0x18001e7cf  sub     rsp, 80h
0x18001e7d6  xor     r14d, r14d
0x18001e7d9  lea     rax, [rbp+hkey]
0x18001e7dd  mov     r12b, cl
0x18001e7e0  mov     [rbp+hkey], r14
0x18001e7e4  xor     r8d, r8d; ulOptions
0x18001e7e7  mov     [rsp+80h+phkResult], rax; phkResult
0x18001e7ec  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x18001e7f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e7fa  lea     r9d, [r14+3]; samDesired
0x18001e7fe  call    cs:__imp_RegOpenKeyExW
0x18001e804  mov     ebx, eax
0x18001e806  test    eax, eax
0x18001e808  jnz     loc_18001EA84
0x18001e80e  mov     rcx, [rbp+hkey]; hkey
0x18001e812  lea     rax, [rbp+arg_10]
0x18001e816  mov     [rsp+80h+pcbData], rax; pcbData
0x18001e81b  lea     r15d, [r14+20h]
0x18001e81f  mov     [rsp+80h+pvData], r14; pvData
0x18001e824  lea     r8, aNullsessionpip; "NullSessionPipes"
0x18001e82b  mov     r9d, r15d; dwFlags
0x18001e82e  mov     [rsp+80h+phkResult], r14; pdwType
0x18001e833  xor     edx, edx; lpSubKey
0x18001e835  mov     [rbp+arg_10], r14d
0x18001e839  call    cs:__imp_RegGetValueW
0x18001e83f  mov     ebx, eax
0x18001e841  test    eax, eax
0x18001e843  jnz     loc_18001EA7A
0x18001e849  mov     eax, [rbp+arg_10]
0x18001e84c  xor     edx, edx; Flags
0x18001e84e  lea     ecx, [rax+50h]
0x18001e851  mov     [rbp+arg_18], ecx
0x18001e854  lea     r8d, [rcx+rax]; Size
0x18001e858  mov     rcx, gs:60h
0x18001e861  mov     rcx, [rcx+30h]; HeapHandle
0x18001e865  call    cs:__imp_RtlAllocateHeap
0x18001e86b  mov     rsi, rax
0x18001e86e  test    rax, rax
0x18001e871  jz      loc_18001EA75
0x18001e877  mov     rcx, [rbp+hkey]; hkey
0x18001e87b  lea     rax, [rbp+arg_10]
0x18001e87f  mov     edi, [rbp+arg_10]
0x18001e882  lea     r8, aNullsessionpip; "NullSessionPipes"
0x18001e889  mov     [rsp+80h+pcbData], rax; pcbData
0x18001e88e  mov     r9d, r15d; dwFlags
0x18001e891  mov     [rsp+80h+pvData], rsi; pvData
0x18001e896  xor     edx, edx; lpSubKey
0x18001e898  mov     [rsp+80h+phkResult], r14; pdwType
0x18001e89d  call    cs:__imp_RegGetValueW
0x18001e8a3  mov     ebx, eax
0x18001e8a5  test    eax, eax
0x18001e8a7  jnz     loc_18001EA5B
0x18001e8ad  shr     rdi, 1
0x18001e8b0  lea     rdx, aNetlogon; "netlogon"
0x18001e8b7  lea     rcx, aSamr; "samr"
0x18001e8be  mov     [rbp+var_20], rdx
0x18001e8c2  lea     rax, aLsarpc; "lsarpc"
0x18001e8c9  mov     [rbp+var_30], rdx
0x18001e8cd  mov     [rbp+var_10], rax
0x18001e8d1  lea     rdx, [rbp+var_20]
0x18001e8d5  xor     eax, eax
0x18001e8d7  mov     [rbp+var_18], rcx
0x18001e8db  mov     word ptr [rbp+pulResult], ax
0x18001e8df  lea     r13, [rsi+rdi*2]
0x18001e8e3  mov     byte ptr [rbp+pulResult+2], al
0x18001e8e6  test    r12b, r12b
0x18001e8e9  lea     rax, [rbp+var_30]
0x18001e8ed  mov     [rbp+var_28], rcx
0x18001e8f1  mov     ecx, [rbp+arg_10]
0x18001e8f4  cmovnz  rdx, rax
0x18001e8f8  mov     eax, ecx
0x18001e8fa  mov     [rbp+var_38], rdx
0x18001e8fe  shr     rax, 1
0x18001e901  mov     r15d, r14d
0x18001e904  cmp     rax, 1
0x18001e908  jz      short loc_18001E973
0x18001e90a  mov     al, r12b
0x18001e90d  neg     al
0x18001e90f  sbb     r14, r14
0x18001e912  add     r14, 3
0x18001e916  xor     r8d, r8d
0x18001e919  mov     rbx, r8
0x18001e91c  lea     rdi, [r15+r15]
0x18001e920  cmp     rbx, r14
0x18001e923  jnb     short loc_18001E948
0x18001e925  mov     rdx, [rdx+rbx*8]; String2
0x18001e929  lea     rcx, [rdi+rsi]; String1
0x18001e92d  call    cs:__imp__wcsicmp
0x18001e933  mov     rdx, [rbp+var_38]
0x18001e937  xor     r8d, r8d
0x18001e93a  test    eax, eax
0x18001e93c  jz      short loc_18001E943
0x18001e93e  inc     rbx
0x18001e941  jmp     short loc_18001E920
0x18001e943  mov     byte ptr [rbp+rbx+pulResult], 1
0x18001e948  lea     rcx, [rdi+rsi]
0x18001e94c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e950  inc     rax
0x18001e953  cmp     [rcx+rax*2], r8w
0x18001e958  jnz     short loc_18001E950
0x18001e95a  mov     ecx, [rbp+arg_10]
0x18001e95d  inc     rax
0x18001e960  add     r15, rax
0x18001e963  mov     eax, ecx
0x18001e965  shr     rax, 1
0x18001e968  dec     rax
0x18001e96b  cmp     r15, rax
0x18001e96e  jb      short loc_18001E919
0x18001e970  xor     r14d, r14d
0x18001e973  mov     r8d, ecx; Size
0x18001e976  mov     rdx, rsi; Src
0x18001e979  mov     rcx, r13; void *
0x18001e97c  call    memcpy_0
0x18001e981  mov     ebx, [rbp+arg_10]
0x18001e984  mov     rdi, r14
0x18001e987  shr     rbx, 1
0x18001e98a  dec     rbx
0x18001e98d  neg     r12b
0x18001e990  mov     r12, [rbp+var_38]
0x18001e994  sbb     r15, r15
0x18001e997  add     r15, 3
0x18001e99b  cmp     rdi, r15
0x18001e99e  jnb     short loc_18001EA0D
0x18001e9a0  cmp     byte ptr [rbp+rdi+pulResult], r14b
0x18001e9a5  jnz     short loc_18001EA01
0x18001e9a7  mov     r14, [r12+rdi*8]
0x18001e9ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e9af  xor     eax, eax
0x18001e9b1  inc     r8
0x18001e9b4  cmp     [r14+r8*2], ax
0x18001e9b9  jnz     short loc_18001E9B1
0x18001e9bb  mov     eax, [rbp+arg_18]
0x18001e9be  lea     rcx, [rbx+2]
0x18001e9c2  add     rcx, r8
0x18001e9c5  shr     rax, 1
0x18001e9c8  cmp     rcx, rax
0x18001e9cb  jnb     short loc_18001EA06
0x18001e9cd  lea     rcx, ds:0[rbx*2]
0x18001e9d5  mov     rdx, r14; Src
0x18001e9d8  add     rcx, r13; void *
0x18001e9db  lea     r8, ds:2[r8*2]; Size
0x18001e9e3  call    memcpy_0
0x18001e9e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e9ec  xor     ecx, ecx
0x18001e9ee  inc     rax
0x18001e9f1  cmp     [r14+rax*2], cx
0x18001e9f6  jnz     short loc_18001E9EE
0x18001e9f8  inc     rbx
0x18001e9fb  add     rbx, rax
0x18001e9fe  xor     r14d, r14d
0x18001ea01  inc     rdi
0x18001ea04  jmp     short loc_18001E99B
0x18001ea06  mov     ebx, 1Fh
0x18001ea0b  jmp     short loc_18001EA5B
0x18001ea0d  lea     rcx, ds:2[rbx*2]; ullOperand
0x18001ea15  mov     [r13+rbx*2+0], r14w
0x18001ea1b  lea     rdx, [rbp+pulResult]; pulResult
0x18001ea1f  mov     [rbp+pulResult], r14d
0x18001ea23  call    ULongLongToULong
0x18001ea28  test    eax, eax
0x18001ea2a  jz      short loc_18001EA33
0x18001ea2c  mov     ebx, 216h
0x18001ea31  jmp     short loc_18001EA5B
0x18001ea33  mov     eax, [rbp+pulResult]
0x18001ea36  lea     rdx, aNullsessionpip; "NullSessionPipes"
0x18001ea3d  mov     rcx, [rbp+hkey]; hKey
0x18001ea41  mov     r9d, 7; dwType
0x18001ea47  mov     dword ptr [rsp+80h+pvData], eax; cbData
0x18001ea4b  xor     r8d, r8d; Reserved
0x18001ea4e  mov     [rsp+80h+phkResult], r13; lpData
0x18001ea53  call    cs:__imp_RegSetValueExW
0x18001ea59  mov     ebx, eax
0x18001ea5b  mov     rcx, gs:60h
0x18001ea64  mov     r8, rsi; P
0x18001ea67  xor     edx, edx; Flags
0x18001ea69  mov     rcx, [rcx+30h]; HeapHandle
0x18001ea6d  call    cs:__imp_RtlFreeHeap
0x18001ea73  jmp     short loc_18001EA7A
0x18001ea75  mov     ebx, 8
0x18001ea7a  mov     rcx, [rbp+hkey]; hKey
0x18001ea7e  call    cs:__imp_RegCloseKey
0x18001ea84  mov     eax, ebx
0x18001ea86  mov     rbx, [rsp+80h+arg_0]
0x18001ea8e  add     rsp, 80h
0x18001ea95  pop     r15
0x18001ea97  pop     r14
0x18001ea99  pop     r13
0x18001ea9b  pop     r12
0x18001ea9d  pop     rdi
0x18001ea9e  pop     rsi
0x18001ea9f  pop     rbp
0x18001eaa0  retn
```
