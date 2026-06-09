# RasEapCreateMethodConfiguration

- ea: `0x180016cb0`
- end: `0x180016e26`
- name: `RasEapCreateMethodConfiguration`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800038d0`
- `0x180003bd0`
- `0x180004690`
- `0x180006a20`
- `0x180016cb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e11`

## pseudocode

```c
__int64 __fastcall RasEapCreateMethodConfiguration(char a1, unsigned int a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  _QWORD *v9; // rcx
  unsigned int v10; // ebx
  unsigned int ConnectionData; // eax
  char v12; // r8
  __int64 i; // r9
  int v14; // edx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HLOCAL v17; // rax
  HLOCAL hMem[9]; // [rsp+20h] [rbp-48h] BYREF

  hMem[0] = 0;
  DebuggingInit(1);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a2 != 26 )
  {
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control )
      WPP_SF_d(v9[2], 190, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, a2);
    return v10;
  }
  if ( !a5 || !a4 )
  {
    v10 = 87;
    if ( v9 == &WPP_GLOBAL_Control )
      return v10;
    WPP_SF_(v9[2], 191, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    goto LABEL_26;
  }
  ConnectionData = ReadConnectionData(a1, 0, 0, hMem);
  v10 = ConnectionData;
  if ( !ConnectionData )
  {
    v12 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *(_DWORD *)a3 )
      {
        v17 = hMem[0];
        if ( v12 )
          *((_DWORD *)hMem[0] + 1) |= 2u;
        else
          *((_DWORD *)hMem[0] + 1) &= ~2u;
        *a4 = 8;
        *a5 = v17;
        return v10;
      }
      v14 = *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * (unsigned int)i);
      if ( (unsigned int)(v14 - 1) > 9 )
        break;
      if ( v14 == 1 )
        v12 = 1;
    }
    v10 = 13;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_26;
    v16 = 192;
    goto LABEL_17;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v16 = 193;
    i = ConnectionData;
LABEL_17:
    WPP_SF_d(v15[2], v16, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, i);
  }
LABEL_26:
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return v10;
}

```

## disassembly

```asm
0x180016cb0  push    rbx
0x180016cb2  push    rbp
0x180016cb3  push    rsi
0x180016cb4  push    rdi
0x180016cb5  push    r14
0x180016cb7  push    r15
0x180016cb9  sub     rsp, 38h
0x180016cbd  mov     ebx, ecx
0x180016cbf  mov     [rsp+68h+hMem], 0
0x180016cc8  mov     ecx, 1
0x180016ccd  mov     rsi, r9
0x180016cd0  mov     rbp, r8
0x180016cd3  mov     edi, edx
0x180016cd5  call    DebuggingInit
0x180016cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ce1  lea     r14, WPP_GLOBAL_Control
0x180016ce8  lea     r15, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180016cef  cmp     rcx, r14
0x180016cf2  jz      short loc_180016D0C
0x180016cf4  mov     rcx, [rcx+10h]
0x180016cf8  mov     edx, 0BDh
0x180016cfd  mov     r8, r15
0x180016d00  call    WPP_SF_
0x180016d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d0c  cmp     edi, 1Ah
0x180016d0f  jz      short loc_180016D36
0x180016d11  mov     ebx, 57h ; 'W'
0x180016d16  cmp     rcx, r14
0x180016d19  jz      loc_180016E17
0x180016d1f  mov     rcx, [rcx+10h]
0x180016d23  lea     edx, [rbx+67h]
0x180016d26  mov     r9d, edi
0x180016d29  mov     r8, r15
0x180016d2c  call    WPP_SF_d
0x180016d31  jmp     loc_180016E17
0x180016d36  mov     rdi, [rsp+68h+arg_20]
0x180016d3e  test    rdi, rdi
0x180016d41  jz      loc_180016DEE
0x180016d47  test    rsi, rsi
0x180016d4a  jz      loc_180016DEE
0x180016d50  lea     r9, [rsp+68h+hMem]
0x180016d55  xor     r8d, r8d
0x180016d58  xor     edx, edx
0x180016d5a  mov     ecx, ebx
0x180016d5c  call    ReadConnectionData
0x180016d61  mov     ebx, eax
0x180016d63  test    eax, eax
0x180016d65  jnz     short loc_180016DD8
0x180016d67  xor     r8b, r8b
0x180016d6a  xor     r9d, r9d
0x180016d6d  cmp     r9d, [rbp+0]
0x180016d71  jnb     short loc_180016DB9
0x180016d73  mov     rax, [rbp+8]
0x180016d77  mov     ecx, r9d
0x180016d7a  add     rcx, rcx
0x180016d7d  mov     edx, [rax+rcx*8]
0x180016d80  lea     eax, [rdx-1]
0x180016d83  cmp     eax, 9
0x180016d86  ja      short loc_180016D95
0x180016d88  cmp     edx, 1
0x180016d8b  jnz     short loc_180016D90
0x180016d8d  mov     r8b, dl
0x180016d90  inc     r9d
0x180016d93  jmp     short loc_180016D6D
0x180016d95  mov     ebx, 0Dh
0x180016d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016da1  cmp     rcx, r14
0x180016da4  jz      short loc_180016E07
0x180016da6  mov     edx, 0C0h
0x180016dab  mov     rcx, [rcx+10h]
0x180016daf  mov     r8, r15
0x180016db2  call    WPP_SF_d
0x180016db7  jmp     short loc_180016E07
0x180016db9  mov     rax, [rsp+68h+hMem]
0x180016dbe  test    r8b, r8b
0x180016dc1  jz      short loc_180016DC9
0x180016dc3  or      dword ptr [rax+4], 2
0x180016dc7  jmp     short loc_180016DCD
0x180016dc9  and     dword ptr [rax+4], 0FFFFFFFDh
0x180016dcd  mov     dword ptr [rsi], 8
0x180016dd3  mov     [rdi], rax
0x180016dd6  jmp     short loc_180016E17
0x180016dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ddf  cmp     rcx, r14
0x180016de2  jz      short loc_180016E07
0x180016de4  mov     edx, 0C1h
0x180016de9  mov     r9d, eax
0x180016dec  jmp     short loc_180016DAB
0x180016dee  mov     ebx, 57h ; 'W'
0x180016df3  cmp     rcx, r14
0x180016df6  jz      short loc_180016E17
0x180016df8  mov     rcx, [rcx+10h]
0x180016dfc  lea     edx, [rbx+68h]
0x180016dff  mov     r8, r15
0x180016e02  call    WPP_SF_
0x180016e07  mov     rcx, [rsp+68h+hMem]; hMem
0x180016e0c  test    rcx, rcx
0x180016e0f  jz      short loc_180016E17
0x180016e11  call    cs:__imp_LocalFree
0x180016e17  mov     eax, ebx
0x180016e19  add     rsp, 38h
0x180016e1d  pop     r15
0x180016e1f  pop     r14
0x180016e21  pop     rdi
0x180016e22  pop     rsi
0x180016e23  pop     rbp
0x180016e24  pop     rbx
0x180016e25  retn
```
