# DwGetDevConfig

- ea: `0x180010c04`
- end: `0x180010d5d`
- name: `DwGetDevConfig`
- size: `345`
- prototype: `__int64 __fastcall(DWORD dwDeviceID)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800107a8`

## callees

- `0x18000d92c`
- `0x180010b48`
- `0x180010c04`
- `0x180029266`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010d3e`

## string_xrefs

- `0x180010c44`: `comm/datamodem`
- `0x180010c51`: `comm/datamodem/dialin`
- `0x180010c73`: `DwGetDevConfig returned error=0x%x`
- `0x180010c8c`: `comm/extendedcaps`

## pseudocode

```c
__int64 __fastcall DwGetDevConfig(DWORD dwDeviceID, _DWORD *a2, unsigned int *a3, int a4)
{
  struct varstring_tag *v4; // rdi
  unsigned int v8; // ebx
  unsigned int v9; // r12d
  const CHAR *v10; // rdx
  unsigned int ConfigInfoForDeviceClass; // eax
  _DWORD *v12; // rbp
  unsigned int v13; // eax
  unsigned int v14; // ecx
  DWORD dwStringSize; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r9
  DWORD v19; // eax
  struct varstring_tag *v21; // [rsp+20h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  hMem = 0;
  v21 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v9 = *a3;
  *a3 = 0;
  v10 = "comm/datamodem/dialin";
  if ( !a4 )
    v10 = "comm/datamodem";
  ConfigInfoForDeviceClass = DwGetConfigInfoForDeviceClass(dwDeviceID, v10, (struct varstring_tag **)&hMem);
  v12 = hMem;
  v8 = ConfigInfoForDeviceClass;
  if ( ConfigInfoForDeviceClass )
  {
    RasTapiTrace("DwGetDevConfig returned error=0x%x");
  }
  else
  {
    DwGetConfigInfoForDeviceClass(dwDeviceID, "comm/extendedcaps", &v21);
    v13 = v12[4];
    v8 = 0;
    v4 = v21;
    v14 = v13 + 20;
    if ( v13 + 20 >= v13 )
    {
      if ( v21 )
        dwStringSize = v21->dwStringSize;
      else
        dwStringSize = 0;
      v16 = v14 + dwStringSize;
      if ( v16 >= v14 )
      {
        *a3 = v16;
        if ( v9 < v16 )
        {
          v8 = 603;
        }
        else
        {
          *a2 = 16;
          v17 = v12[4];
          a2[1] = v17;
          memcpy_0(a2 + 4, (char *)v12 + (unsigned int)v12[5], v17);
          if ( v4 )
          {
            v18 = (unsigned int)a2[1];
            a2[2] = v18 + *a2;
            v19 = v4->dwStringSize;
            a2[3] = v19;
            memcpy_0((char *)a2 + v18 + 16, (char *)v4 + v4->dwStringOffset, v19);
          }
          else
          {
            *((_QWORD *)a2 + 1) = 0;
          }
        }
        goto LABEL_19;
      }
      *a3 = -1;
    }
    v8 = 534;
  }
LABEL_19:
  if ( v12 )
    LocalFree(v12);
  if ( v4 )
    LocalFree(v4);
  return v8;
}

```

## disassembly

```asm
0x180010c04  mov     rax, rsp
0x180010c07  mov     [rax+8], rbx
0x180010c0b  mov     [rax+10h], rbp
0x180010c0f  push    rsi
0x180010c10  push    rdi
0x180010c11  push    r12
0x180010c13  push    r14
0x180010c15  push    r15
0x180010c17  sub     rsp, 30h
0x180010c1b  xor     edi, edi
0x180010c1d  mov     qword ptr [rax+18h], 0
0x180010c25  mov     [rax-38h], rdi
0x180010c29  mov     r14, r8
0x180010c2c  mov     rsi, rdx
0x180010c2f  mov     r15d, ecx
0x180010c32  test    r8, r8
0x180010c35  jnz     short loc_180010C41
0x180010c37  mov     ebx, 80070057h
0x180010c3c  jmp     loc_180010D44
0x180010c41  mov     r12d, [r8]
0x180010c44  lea     rax, SubStr; "comm/datamodem"
0x180010c4b  test    r9d, r9d
0x180010c4e  mov     [r8], edi
0x180010c51  lea     rdx, aCommDatamodemD; "comm/datamodem/dialin"
0x180010c58  cmovz   rdx, rax; lpszDeviceClass
0x180010c5c  lea     r8, [rsp+58h+hMem]
0x180010c61  call    DwGetConfigInfoForDeviceClass
0x180010c66  mov     rbp, [rsp+58h+hMem]
0x180010c6b  mov     ebx, eax
0x180010c6d  test    eax, eax
0x180010c6f  jz      short loc_180010C84
0x180010c71  mov     edx, eax
0x180010c73  lea     rcx, aDwgetdevconfig; "DwGetDevConfig returned error=0x%x"
0x180010c7a  call    RasTapiTrace
0x180010c7f  jmp     loc_180010D28
0x180010c84  lea     r8, [rsp+58h+var_38]
0x180010c89  mov     ecx, r15d; dwDeviceID
0x180010c8c  lea     rdx, aCommExtendedca; "comm/extendedcaps"
0x180010c93  call    DwGetConfigInfoForDeviceClass
0x180010c98  mov     eax, [rbp+10h]
0x180010c9b  xor     ebx, ebx
0x180010c9d  mov     rdi, [rsp+58h+var_38]
0x180010ca2  lea     ecx, [rax+14h]
0x180010ca5  cmp     ecx, eax
0x180010ca7  jb      short loc_180010D23
0x180010ca9  test    rdi, rdi
0x180010cac  jz      short loc_180010CB3
0x180010cae  mov     eax, [rdi+10h]
0x180010cb1  jmp     short loc_180010CB5
0x180010cb3  xor     eax, eax
0x180010cb5  add     eax, ecx
0x180010cb7  cmp     eax, ecx
0x180010cb9  jb      short loc_180010D1C
0x180010cbb  mov     [r14], eax
0x180010cbe  cmp     r12d, eax
0x180010cc1  jb      short loc_180010D15
0x180010cc3  mov     dword ptr [rsi], 10h
0x180010cc9  lea     rcx, [rsi+10h]; void *
0x180010ccd  mov     eax, [rbp+10h]
0x180010cd0  mov     [rsi+4], eax
0x180010cd3  mov     r8d, eax; Size
0x180010cd6  mov     edx, [rbp+14h]
0x180010cd9  add     rdx, rbp; Src
0x180010cdc  call    memcpy_0
0x180010ce1  test    rdi, rdi
0x180010ce4  jz      short loc_180010D0F
0x180010ce6  mov     r9d, [rsi+4]
0x180010cea  mov     ecx, [rsi]
0x180010cec  add     ecx, r9d
0x180010cef  mov     [rsi+8], ecx
0x180010cf2  mov     eax, [rdi+10h]
0x180010cf5  lea     rcx, [r9+10h]
0x180010cf9  mov     [rsi+0Ch], eax
0x180010cfc  mov     r8d, eax; Size
0x180010cff  mov     edx, [rdi+14h]
0x180010d02  add     rcx, rsi; void *
0x180010d05  add     rdx, rdi; Src
0x180010d08  call    memcpy_0
0x180010d0d  jmp     short loc_180010D28
0x180010d0f  mov     [rsi+8], rbx
0x180010d13  jmp     short loc_180010D28
0x180010d15  mov     ebx, 25Bh
0x180010d1a  jmp     short loc_180010D28
0x180010d1c  mov     dword ptr [r14], 0FFFFFFFFh
0x180010d23  mov     ebx, 216h
0x180010d28  test    rbp, rbp
0x180010d2b  jz      short loc_180010D36
0x180010d2d  mov     rcx, rbp; hMem
0x180010d30  call    cs:__imp_LocalFree
0x180010d36  test    rdi, rdi
0x180010d39  jz      short loc_180010D44
0x180010d3b  mov     rcx, rdi; hMem
0x180010d3e  call    cs:__imp_LocalFree
0x180010d44  mov     rbp, [rsp+58h+arg_8]
0x180010d49  mov     eax, ebx
0x180010d4b  mov     rbx, [rsp+58h+arg_0]
0x180010d50  add     rsp, 30h
0x180010d54  pop     r15
0x180010d56  pop     r14
0x180010d58  pop     r12
0x180010d5a  pop     rdi
0x180010d5b  pop     rsi
0x180010d5c  retn
```
