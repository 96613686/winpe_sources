# OneXCopyAuthParams

- ea: `0x180018e50`
- end: `0x180019070`
- name: `OneXCopyAuthParams`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005440`
- `0x180010ae0`
- `0x180018e50`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f96`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018f82`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018f57`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180018ef5`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180018ef5`
- `MobileNetworking!FreeMemory` at `0x180019026`
- `MobileNetworking!FreeMemory` at `0x180019026`

## string_xrefs

- `0x18001901a`: `OneXCopyAuthParams`

## pseudocode

```c
__int64 __fastcall OneXCopyAuthParams(unsigned int a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  void *v12; // rbp
  __int64 v13; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v15; // rax
  __int64 v16; // rcx
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v18 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 189, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v6[7], 190, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( !a2 || !a3 )
  {
    v8 = 87;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 1) != 0 )
      WPP_SF_(v6[7], 191, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
    goto LABEL_28;
  }
  LastError = AllocateAndCopyPointerData(&v18, a2, a1);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_28;
    v10 = 192;
LABEL_20:
    WPP_SF_d(v9[7], v10, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, LastError);
LABEL_28:
    FreeMemory(&v18, "OneXCopyAuthParams", 1893);
    goto LABEL_29;
  }
  v11 = 0;
  if ( (*(_BYTE *)(a2 + 20) & 2) != 0 && *(_QWORD *)(a2 + 32) )
  {
    v12 = *(void **)(a2 + 32);
    v13 = v18;
    CurrentProcess = GetCurrentProcess();
    v15 = GetCurrentProcess();
    if ( !DuplicateHandle(v15, v12, CurrentProcess, (LPHANDLE)(v13 + 32), 0, 0, 2u) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_28;
        v10 = 193;
        goto LABEL_20;
      }
    }
    v11 = 1;
  }
  v16 = v18;
  *a3 = v18;
  if ( v8 )
  {
    if ( v11 )
      CloseHandle(*(HANDLE *)(v16 + 32));
    goto LABEL_28;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 194, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180018e50  push    rbx
0x180018e52  sub     rsp, 50h
0x180018e56  mov     [rsp+58h+arg_0], rbp
0x180018e5b  mov     ebx, ecx
0x180018e5d  mov     [rsp+58h+var_10], r14
0x180018e62  mov     rbp, rdx
0x180018e65  mov     [rsp+58h+var_18], r15
0x180018e6a  mov     r14, r8
0x180018e6d  mov     [rsp+58h+arg_8], 0
0x180018e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e7d  lea     r15, WPP_GLOBAL_Control
0x180018e84  cmp     rcx, r15
0x180018e87  jz      short loc_180018ED8
0x180018e89  test    dword ptr [rcx+44h], 800h
0x180018e90  jz      short loc_180018EAE
0x180018e92  mov     rcx, [rcx+38h]
0x180018e96  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180018e9d  mov     edx, 0BDh
0x180018ea2  call    WPP_SF_
0x180018ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018eae  cmp     rcx, r15
0x180018eb1  jz      short loc_180018ED8
0x180018eb3  test    dword ptr [rcx+44h], 100h
0x180018eba  jz      short loc_180018ED8
0x180018ebc  mov     rcx, [rcx+38h]
0x180018ec0  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180018ec7  mov     edx, 0BEh
0x180018ecc  call    WPP_SF_
0x180018ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ed8  test    rbp, rbp
0x180018edb  jz      loc_180018FEF
0x180018ee1  test    r14, r14
0x180018ee4  jz      loc_180018FEF
0x180018eea  mov     r8d, ebx
0x180018eed  lea     rcx, [rsp+58h+arg_8]
0x180018ef2  mov     rdx, rbp
0x180018ef5  call    cs:__imp_AllocateAndCopyPointerData
0x180018efb  mov     ebx, eax
0x180018efd  test    eax, eax
0x180018eff  jz      short loc_180018F25
0x180018f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f08  cmp     rcx, r15
0x180018f0b  jz      loc_180019014
0x180018f11  test    byte ptr [rcx+44h], 1
0x180018f15  jz      loc_180019014
0x180018f1b  mov     edx, 0C0h
0x180018f20  jmp     loc_180018FB9
0x180018f25  xor     eax, eax
0x180018f27  test    byte ptr [rbp+14h], 2
0x180018f2b  jz      loc_180018FD3
0x180018f31  cmp     [rbp+20h], rax
0x180018f35  jz      loc_180018FD3
0x180018f3b  mov     rbp, [rbp+20h]
0x180018f3f  mov     [rsp+58h+arg_10], rsi
0x180018f44  mov     rsi, [rsp+58h+arg_8]
0x180018f49  mov     [rsp+58h+arg_18], rdi
0x180018f4e  call    cs:__imp_GetCurrentProcess
0x180018f54  mov     rdi, rax
0x180018f57  call    cs:__imp_GetCurrentProcess
0x180018f5d  mov     [rsp+58h+dwOptions], 2; dwOptions
0x180018f65  lea     r9, [rsi+20h]; lpTargetHandle
0x180018f69  mov     rcx, rax; hSourceProcessHandle
0x180018f6c  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x180018f74  mov     r8, rdi; hTargetProcessHandle
0x180018f77  mov     [rsp+58h+dwDesiredAccess], 0; dwDesiredAccess
0x180018f7f  mov     rdx, rbp; hSourceHandle
0x180018f82  call    cs:__imp_DuplicateHandle
0x180018f88  mov     rdi, [rsp+58h+arg_18]
0x180018f8d  mov     rsi, [rsp+58h+arg_10]
0x180018f92  test    eax, eax
0x180018f94  jnz     short loc_180018FCE
0x180018f96  call    cs:__imp_GetLastError
0x180018f9c  mov     ebx, eax
0x180018f9e  test    eax, eax
0x180018fa0  jz      short loc_180018FCE
0x180018fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fa9  cmp     rcx, r15
0x180018fac  jz      short loc_180019014
0x180018fae  test    byte ptr [rcx+44h], 1
0x180018fb2  jz      short loc_180019014
0x180018fb4  mov     edx, 0C1h
0x180018fb9  mov     rcx, [rcx+38h]
0x180018fbd  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180018fc4  mov     r9d, eax
0x180018fc7  call    WPP_SF_d
0x180018fcc  jmp     short loc_180019014
0x180018fce  mov     eax, 1
0x180018fd3  mov     rcx, [rsp+58h+arg_8]
0x180018fd8  mov     [r14], rcx
0x180018fdb  test    ebx, ebx
0x180018fdd  jz      short loc_18001902C
0x180018fdf  test    eax, eax
0x180018fe1  jz      short loc_180019014
0x180018fe3  mov     rcx, [rcx+20h]; hObject
0x180018fe7  call    cs:__imp_CloseHandle
0x180018fed  jmp     short loc_180019014
0x180018fef  mov     ebx, 57h ; 'W'
0x180018ff4  cmp     rcx, r15
0x180018ff7  jz      short loc_180019014
0x180018ff9  test    byte ptr [rcx+44h], 1
0x180018ffd  jz      short loc_180019014
0x180018fff  mov     rcx, [rcx+38h]
0x180019003  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001900a  mov     edx, 0BFh
0x18001900f  call    WPP_SF_
0x180019014  mov     r8d, 765h
0x18001901a  lea     rdx, aOnexcopyauthpa_0; "OneXCopyAuthParams"
0x180019021  lea     rcx, [rsp+58h+arg_8]
0x180019026  call    cs:__imp_FreeMemory
0x18001902c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019033  mov     r14, [rsp+58h+var_10]
0x180019038  cmp     rcx, r15
0x18001903b  mov     r15, [rsp+58h+var_18]
0x180019040  mov     rbp, [rsp+58h+arg_0]
0x180019045  jz      short loc_180019068
0x180019047  test    dword ptr [rcx+44h], 800h
0x18001904e  jz      short loc_180019068
0x180019050  mov     rcx, [rcx+38h]
0x180019054  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001905b  mov     edx, 0C2h
0x180019060  mov     r9d, ebx
0x180019063  call    WPP_SF_D
0x180019068  mov     eax, ebx
0x18001906a  add     rsp, 50h
0x18001906e  pop     rbx
0x18001906f  retn
```
