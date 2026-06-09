# TDSLSetArray<CDSLPropertyInformationSet,CDSLPropertyInformation>::Free(int)

- ea: `0x180055ae0`
- end: `0x180055b6c`
- name: `?Free@?$TDSLSetArray@VCDSLPropertyInformationSet@@VCDSLPropertyInformation@@@@QEAAXH@Z`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d6d8`
- `0x1800553c0`

## callees

- `0x180055ae0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180055b22`
- `OLEAUT32!__imp_VariantClear` at `0x180055b22`
- `ole32!CoTaskMemFree` at `0x180055b30`
- `ole32!CoTaskMemFree` at `0x180055b4d`
- `ole32!CoTaskMemFree` at `0x180055b30`
- `ole32!CoTaskMemFree` at `0x180055b4d`

## pseudocode

```c
void __fastcall TDSLSetArray<CDSLPropertyInformationSet,CDSLPropertyInformation>::Free(int *a1)
{
  LPVOID *v1; // rdi
  int v3; // esi
  LPVOID *v4; // r13
  LPVOID *v5; // r14
  int v6; // ebp
  VARIANTARG *i; // r15
  VARIANTARG *v8; // rcx

  v1 = (LPVOID *)*((_QWORD *)a1 + 1);
  if ( v1 )
  {
    v3 = *a1;
    while ( v3 )
    {
      v4 = v1;
      v5 = v1;
      --v3;
      v1 += 4;
      v6 = *((_DWORD *)v4 + 2);
      for ( i = (VARIANTARG *)*v4; v6; --v6 )
      {
        v8 = i;
        i += 2;
        VariantClear(v8 + 1);
      }
      CoTaskMemFree(*v5);
      *v5 = 0;
      *((_DWORD *)v4 + 2) = 0;
    }
    CoTaskMemFree(*((LPVOID *)a1 + 1));
    *((_QWORD *)a1 + 1) = 0;
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180055ae0  push    rbx
0x180055ae2  push    rbp
0x180055ae3  push    rsi
0x180055ae4  push    rdi
0x180055ae5  push    r13
0x180055ae7  push    r14
0x180055ae9  push    r15
0x180055aeb  sub     rsp, 20h
0x180055aef  mov     rdi, [rcx+8]
0x180055af3  mov     rbx, rcx
0x180055af6  test    rdi, rdi
0x180055af9  jz      short loc_180055B5D
0x180055afb  mov     esi, [rcx]
0x180055afd  jmp     short loc_180055B45
0x180055aff  mov     r13, rdi
0x180055b02  mov     r14, rdi
0x180055b05  dec     esi
0x180055b07  add     rdi, 20h ; ' '
0x180055b0b  mov     ebp, [r13+8]
0x180055b0f  mov     r15, [r13+0]
0x180055b13  test    ebp, ebp
0x180055b15  jz      short loc_180055B2D
0x180055b17  mov     rcx, r15
0x180055b1a  add     r15, 30h ; '0'
0x180055b1e  add     rcx, 18h; pvarg
0x180055b22  call    cs:__imp_VariantClear
0x180055b28  sub     ebp, 1
0x180055b2b  jnz     short loc_180055B17
0x180055b2d  mov     rcx, [r14]; pv
0x180055b30  call    cs:__imp_CoTaskMemFree
0x180055b36  mov     qword ptr [r14], 0
0x180055b3d  mov     dword ptr [r13+8], 0
0x180055b45  test    esi, esi
0x180055b47  jnz     short loc_180055AFF
0x180055b49  mov     rcx, [rbx+8]; pv
0x180055b4d  call    cs:__imp_CoTaskMemFree
0x180055b53  mov     qword ptr [rbx+8], 0
0x180055b5b  mov     [rbx], esi
0x180055b5d  add     rsp, 20h
0x180055b61  pop     r15
0x180055b63  pop     r14
0x180055b65  pop     r13
0x180055b67  pop     rdi
0x180055b68  pop     rsi
0x180055b69  pop     rbp
0x180055b6a  pop     rbx
0x180055b6b  retn
```
