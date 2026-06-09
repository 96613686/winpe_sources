# CADMCOMW::GetData(ulong,ushort const *,_METADATA_RECORD *,ulong *)

- ea: `0x180005a20`
- end: `0x180005bbe`
- name: `?GetData@CADMCOMW@@UEAAJKPEBGPEAU_METADATA_RECORD@@PEAK@Z`
- size: `414`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005a20`
- `0x180006e44`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetData(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4,
        unsigned int *a5)
{
  DWORD dwMDAttributes; // eax
  unsigned int *v10; // rdi
  DWORD v11; // esi
  __int64 result; // rax
  int v13; // esi
  __int64 v14; // rcx
  DWORD v15; // edx
  char v16; // cl
  unsigned __int8 *pbMDData; // rcx
  __int64 dwMDDataLen; // rdx
  int v19; // [rsp+60h] [rbp-38h] BYREF
  int v20; // [rsp+64h] [rbp-34h] BYREF
  __int64 v21; // [rsp+68h] [rbp-30h] BYREF
  unsigned int v22; // [rsp+B8h] [rbp+20h] BYREF

  v22 = 0;
  v20 = 0;
  v19 = 0;
  if ( !a4 || a4->dwMDDataLen && !a4->pbMDData )
    return 2147942487LL;
  dwMDAttributes = a4->dwMDAttributes;
  if ( (dwMDAttributes & 8) != 0 || (dwMDAttributes & 3) == 2 || a4->dwMDDataType >= 6 )
    return 2147942487LL;
  v10 = a5;
  if ( a5 )
    *a5 = 0;
  v11 = a4->dwMDAttributes;
  result = CADMCOMW::LookupAndAccessCheck(this, a2, &v22, (__int64)a3, 5u, 0, (__int64)a4, (__int64)&v20, &v21, &v19, 0);
  if ( (int)result >= 0 )
  {
    a4->dwMDAttributes |= 0x20u;
    v13 = v11 & 0x20;
    v14 = *((_QWORD *)this + 101);
    if ( v14 && v19 == 1 )
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int *))(*(_QWORD *)v14 + 48LL))(
                 v14,
                 v22,
                 a3,
                 a4,
                 v10);
    else
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int *))(**((_QWORD **)this + 4) + 168LL))(
                 *((_QWORD *)this + 4),
                 v22,
                 a3,
                 a4,
                 v10);
    v15 = a4->dwMDAttributes;
    v16 = v15;
    if ( !v13 )
    {
      v16 = v15 & 0xDF;
      a4->dwMDAttributes = v15 & 0xFFFFFFDF;
    }
    if ( (int)result >= 0 && (v16 & 4) != 0 )
    {
      if ( v20 )
      {
        if ( (v15 & 0x20) == 0 )
          return result;
        result = CADMCOMW::IsReadAccessGranted(this, a2, a3, a4);
        if ( (int)result >= 0 )
          return result;
      }
      else
      {
        result = 2147942405LL;
      }
      if ( v10 )
        *v10 = 0;
      pbMDData = a4->pbMDData;
      if ( pbMDData )
      {
        dwMDDataLen = a4->dwMDDataLen;
        if ( a4->dwMDDataLen )
        {
          do
          {
            *pbMDData++ = 0;
            --dwMDDataLen;
          }
          while ( dwMDDataLen );
        }
      }
      a4->dwMDDataLen = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005a20  mov     rax, rsp
0x180005a23  mov     [rax+8], rbx
0x180005a27  mov     [rax+10h], rbp
0x180005a2b  push    rsi
0x180005a2c  push    rdi
0x180005a2d  push    r12
0x180005a2f  push    r14
0x180005a31  push    r15
0x180005a33  sub     rsp, 70h
0x180005a37  xor     r12d, r12d
0x180005a3a  mov     rbx, r9
0x180005a3d  mov     [rax+20h], r12d
0x180005a41  mov     r14, r8
0x180005a44  mov     [rax-34h], r12d
0x180005a48  mov     r15d, edx
0x180005a4b  mov     [rax-38h], r12d
0x180005a4f  mov     rbp, rcx
0x180005a52  test    r9, r9
0x180005a55  jz      loc_180005BA0
0x180005a5b  cmp     [r9+10h], r12d
0x180005a5f  jz      short loc_180005A6B
0x180005a61  cmp     [r9+18h], r12
0x180005a65  jz      loc_180005BA0
0x180005a6b  mov     eax, [r9+4]
0x180005a6f  test    al, 8
0x180005a71  jnz     loc_180005BA0
0x180005a77  and     al, 3
0x180005a79  cmp     al, 2
0x180005a7b  jz      loc_180005BA0
0x180005a81  cmp     dword ptr [r9+0Ch], 6
0x180005a86  jnb     loc_180005BA0
0x180005a8c  mov     rdi, [rsp+98h+arg_20]
0x180005a94  test    rdi, rdi
0x180005a97  jz      short loc_180005A9C
0x180005a99  mov     [rdi], r12d
0x180005a9c  mov     esi, [r9+4]
0x180005aa0  lea     rax, [rsp+98h+var_38]
0x180005aa5  mov     [rsp+98h+var_48], r12
0x180005aaa  lea     r8, [rsp+98h+arg_18]
0x180005ab2  mov     [rsp+98h+var_50], rax
0x180005ab7  mov     r9, r14
0x180005aba  lea     rax, [rsp+98h+var_30]
0x180005abf  mov     [rsp+98h+var_58], rax
0x180005ac4  lea     rax, [rsp+98h+var_34]
0x180005ac9  mov     [rsp+98h+var_60], rax
0x180005ace  mov     [rsp+98h+var_68], rbx
0x180005ad3  mov     [rsp+98h+var_70], r12d
0x180005ad8  mov     dword ptr [rsp+98h+var_78], 5
0x180005ae0  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180005ae5  test    eax, eax
0x180005ae7  js      loc_180005BA5
0x180005aed  or      dword ptr [rbx+4], 20h
0x180005af1  and     esi, 20h
0x180005af4  mov     rcx, [rbp+328h]
0x180005afb  test    rcx, rcx
0x180005afe  jz      short loc_180005B10
0x180005b00  cmp     [rsp+98h+var_38], 1
0x180005b05  jnz     short loc_180005B10
0x180005b07  mov     rax, [rcx]
0x180005b0a  mov     rax, [rax+30h]
0x180005b0e  jmp     short loc_180005B1E
0x180005b10  mov     rcx, [rbp+20h]
0x180005b14  mov     rax, [rcx]
0x180005b17  mov     rax, [rax+0A8h]
0x180005b1e  mov     edx, [rsp+98h+arg_18]
0x180005b25  mov     r9, rbx
0x180005b28  mov     r8, r14
0x180005b2b  mov     [rsp+98h+var_78], rdi
0x180005b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b35  mov     edx, [rbx+4]
0x180005b38  mov     ecx, edx
0x180005b3a  test    esi, esi
0x180005b3c  jnz     short loc_180005B44
0x180005b3e  and     ecx, 0FFFFFFDFh
0x180005b41  mov     [rbx+4], ecx
0x180005b44  test    eax, eax
0x180005b46  js      short loc_180005BA5
0x180005b48  test    cl, 4
0x180005b4b  jz      short loc_180005BA5
0x180005b4d  cmp     [rsp+98h+var_34], r12d
0x180005b52  jnz     short loc_180005B5B
0x180005b54  mov     eax, 80070005h
0x180005b59  jmp     short loc_180005B75
0x180005b5b  test    dl, 20h
0x180005b5e  jz      short loc_180005BA5
0x180005b60  mov     r9, rbx; struct _METADATA_RECORD *
0x180005b63  mov     r8, r14; unsigned __int16 *
0x180005b66  mov     edx, r15d; unsigned int
0x180005b69  mov     rcx, rbp; this
0x180005b6c  call    ?IsReadAccessGranted@CADMCOMW@@QEAAJKPEBGPEAU_METADATA_RECORD@@@Z; CADMCOMW::IsReadAccessGranted(ulong,ushort const *,_METADATA_RECORD *)
0x180005b71  test    eax, eax
0x180005b73  jns     short loc_180005BA5
0x180005b75  test    rdi, rdi
0x180005b78  jz      short loc_180005B7D
0x180005b7a  mov     [rdi], r12d
0x180005b7d  mov     rcx, [rbx+18h]
0x180005b81  test    rcx, rcx
0x180005b84  jz      short loc_180005B9A
0x180005b86  mov     edx, [rbx+10h]
0x180005b89  test    rdx, rdx
0x180005b8c  jz      short loc_180005B9A
0x180005b8e  mov     [rcx], r12b
0x180005b91  inc     rcx
0x180005b94  sub     rdx, 1
0x180005b98  jnz     short loc_180005B8E
0x180005b9a  mov     [rbx+10h], r12d
0x180005b9e  jmp     short loc_180005BA5
0x180005ba0  mov     eax, 80070057h
0x180005ba5  lea     r11, [rsp+98h+var_28]
0x180005baa  mov     rbx, [r11+30h]
0x180005bae  mov     rbp, [r11+38h]
0x180005bb2  mov     rsp, r11
0x180005bb5  pop     r15
0x180005bb7  pop     r14
0x180005bb9  pop     r12
0x180005bbb  pop     rdi
0x180005bbc  pop     rsi
0x180005bbd  retn
```
