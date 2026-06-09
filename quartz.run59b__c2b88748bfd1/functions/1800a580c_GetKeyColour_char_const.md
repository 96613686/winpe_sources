# GetKeyColour(char const *)

- ea: `0x1800a580c`
- end: `0x1800a58c0`
- name: `?GetKeyColour@@YAKPEBD@Z`
- size: `180`
- prototype: `unsigned int __fastcall(PCNZCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a5c44`

## callees

- `0x1800a580c`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x1800a583d`
- `KERNEL32!CompareStringA` at `0x1800a583d`
- `GDI32!DeleteDC` at `0x1800a5893`
- `GDI32!DeleteDC` at `0x1800a5893`
- `GDI32!CreateDCA` at `0x1800a5860`
- `GDI32!CreateDCA` at `0x1800a5860`
- `GDI32!GetDeviceCaps` at `0x1800a587c`
- `GDI32!GetDeviceCaps` at `0x1800a587c`

## pseudocode

```c
HDC __fastcall GetKeyColour(PCNZCH lpString1)
{
  const CHAR *v2; // rdx
  const CHAR *v3; // rcx
  HDC result; // rax
  HDC v5; // rdi
  int v6; // ebx

  if ( !lpString1 || CompareStringA(0x7Fu, 1u, lpString1, -1, "DISPLAY", -1) == 2 )
  {
    v2 = 0;
    v3 = "DISPLAY";
  }
  else
  {
    v2 = lpString1;
    v3 = 0;
  }
  result = CreateDCA(v3, v2, 0, 0);
  v5 = result;
  if ( result )
  {
    v6 = GetDeviceCaps(result, 38) & 0x100;
    DeleteDC(v5);
    return (HDC)*(unsigned int *)((char *)&qword_18017C868 + (v6 == 0 ? 4 : 0));
  }
  return result;
}

```

## disassembly

```asm
0x1800a580c  mov     [rsp+arg_0], rbx
0x1800a5811  push    rdi
0x1800a5812  sub     rsp, 30h
0x1800a5816  lea     rdi, pwszDriver; "DISPLAY"
0x1800a581d  mov     rbx, rcx
0x1800a5820  test    rcx, rcx
0x1800a5823  jz      short loc_1800A5855
0x1800a5825  or      r9d, 0FFFFFFFFh; cchCount1
0x1800a5829  mov     r8, rcx; lpString1
0x1800a582c  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800a5831  mov     [rsp+38h+lpString2], rdi; lpString2
0x1800a5836  lea     edx, [r9+2]; dwCmpFlags
0x1800a583a  lea     ecx, [rdx+7Eh]; Locale
0x1800a583d  call    cs:__imp_CompareStringA
0x1800a5844  nop     dword ptr [rax+rax+00h]
0x1800a5849  cmp     eax, 2
0x1800a584c  jz      short loc_1800A5855
0x1800a584e  mov     rdx, rbx
0x1800a5851  xor     ecx, ecx
0x1800a5853  jmp     short loc_1800A585A
0x1800a5855  xor     edx, edx; pwszDevice
0x1800a5857  mov     rcx, rdi; pwszDriver
0x1800a585a  xor     r9d, r9d; pdm
0x1800a585d  xor     r8d, r8d; pszPort
0x1800a5860  call    cs:__imp_CreateDCA
0x1800a5867  nop     dword ptr [rax+rax+00h]
0x1800a586c  mov     rdi, rax
0x1800a586f  test    rax, rax
0x1800a5872  jz      short loc_1800A58B4
0x1800a5874  mov     edx, 26h ; '&'; index
0x1800a5879  mov     rcx, rdi; hdc
0x1800a587c  call    cs:__imp_GetDeviceCaps
0x1800a5883  nop     dword ptr [rax+rax+00h]
0x1800a5888  mov     ebx, eax
0x1800a588a  mov     rcx, rdi; hdc
0x1800a588d  and     ebx, 100h
0x1800a5893  call    cs:__imp_DeleteDC
0x1800a589a  nop     dword ptr [rax+rax+00h]
0x1800a589f  neg     ebx
0x1800a58a1  lea     rcx, qword_18017C868
0x1800a58a8  sbb     rax, rax
0x1800a58ab  not     rax
0x1800a58ae  and     eax, 4
0x1800a58b1  mov     eax, [rax+rcx]
0x1800a58b4  mov     rbx, [rsp+38h+arg_0]
0x1800a58b9  add     rsp, 30h
0x1800a58bd  pop     rdi
0x1800a58be  retn
```
