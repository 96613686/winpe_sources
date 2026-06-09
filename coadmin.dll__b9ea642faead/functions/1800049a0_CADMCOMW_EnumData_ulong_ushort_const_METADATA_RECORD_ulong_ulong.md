# CADMCOMW::EnumData(ulong,ushort const *,_METADATA_RECORD *,ulong,ulong *)

- ea: `0x1800049a0`
- end: `0x180004b44`
- name: `?EnumData@CADMCOMW@@UEAAJKPEBGPEAU_METADATA_RECORD@@KPEAK@Z`
- size: `420`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800049a0`
- `0x180006e44`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::EnumData(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4,
        unsigned int a5,
        unsigned int *a6)
{
  DWORD dwMDAttributes; // eax
  unsigned int *v11; // rdi
  DWORD v12; // esi
  __int64 result; // rax
  int v14; // esi
  __int64 v15; // rcx
  DWORD v16; // edx
  char v17; // cl
  unsigned __int8 *pbMDData; // rcx
  __int64 dwMDDataLen; // rdx
  int v20; // [rsp+60h] [rbp-38h] BYREF
  _DWORD v21[3]; // [rsp+64h] [rbp-34h] BYREF
  unsigned int v22; // [rsp+B8h] [rbp+20h] BYREF

  v22 = 0;
  v21[0] = 0;
  v20 = 0;
  if ( !a4 || a4->dwMDDataLen && !a4->pbMDData )
    return 2147942487LL;
  dwMDAttributes = a4->dwMDAttributes;
  if ( (dwMDAttributes & 8) != 0 || (dwMDAttributes & 3) == 2 || a4->dwMDDataType >= 6 )
    return 2147942487LL;
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = a4->dwMDAttributes;
  result = CADMCOMW::LookupAndAccessCheck(this, a2, &v22, (__int64)a3, 1u, 0, 0, (__int64)v21, 0, &v20, 0);
  if ( (int)result >= 0 )
  {
    a4->dwMDAttributes |= 0x20u;
    v14 = v12 & 0x20;
    v15 = *((_QWORD *)this + 101);
    if ( v15 && v20 == 1 )
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int, unsigned int *))(*(_QWORD *)v15 + 80LL))(
                 v15,
                 v22,
                 a3,
                 a4,
                 a5,
                 v11);
    else
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, struct _METADATA_RECORD *, unsigned int, unsigned int *))(**((_QWORD **)this + 4) + 200LL))(
                 *((_QWORD *)this + 4),
                 v22,
                 a3,
                 a4,
                 a5,
                 v11);
    v16 = a4->dwMDAttributes;
    v17 = v16;
    if ( !v14 )
    {
      v17 = v16 & 0xDF;
      a4->dwMDAttributes = v16 & 0xFFFFFFDF;
    }
    if ( (int)result >= 0 && (v17 & 4) != 0 )
    {
      if ( v21[0] )
      {
        if ( (v16 & 0x20) == 0 )
          return result;
        result = CADMCOMW::IsReadAccessGranted(this, a2, a3, a4);
        if ( (int)result >= 0 )
          return result;
      }
      else
      {
        result = 2147942405LL;
      }
      if ( v11 )
        *v11 = 0;
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
0x1800049a0  mov     rax, rsp
0x1800049a3  mov     [rax+8], rbx
0x1800049a7  mov     [rax+10h], rbp
0x1800049ab  push    rsi
0x1800049ac  push    rdi
0x1800049ad  push    r12
0x1800049af  push    r14
0x1800049b1  push    r15
0x1800049b3  sub     rsp, 70h
0x1800049b7  xor     r12d, r12d
0x1800049ba  mov     rbx, r9
0x1800049bd  mov     [rax+20h], r12d
0x1800049c1  mov     r14, r8
0x1800049c4  mov     [rax-34h], r12d
0x1800049c8  mov     r15d, edx
0x1800049cb  mov     [rax-38h], r12d
0x1800049cf  mov     rbp, rcx
0x1800049d2  test    r9, r9
0x1800049d5  jz      loc_180004B26
0x1800049db  cmp     [r9+10h], r12d
0x1800049df  jz      short loc_1800049EB
0x1800049e1  cmp     [r9+18h], r12
0x1800049e5  jz      loc_180004B26
0x1800049eb  mov     eax, [r9+4]
0x1800049ef  test    al, 8
0x1800049f1  jnz     loc_180004B26
0x1800049f7  and     al, 3
0x1800049f9  cmp     al, 2
0x1800049fb  jz      loc_180004B26
0x180004a01  cmp     dword ptr [r9+0Ch], 6
0x180004a06  jnb     loc_180004B26
0x180004a0c  mov     rdi, [rsp+98h+arg_28]
0x180004a14  test    rdi, rdi
0x180004a17  jz      short loc_180004A1C
0x180004a19  mov     [rdi], r12d
0x180004a1c  mov     esi, [r9+4]
0x180004a20  lea     rax, [rsp+98h+var_38]
0x180004a25  mov     [rsp+98h+var_48], r12
0x180004a2a  lea     r8, [rsp+98h+arg_18]
0x180004a32  mov     [rsp+98h+var_50], rax
0x180004a37  mov     r9, r14
0x180004a3a  mov     [rsp+98h+var_58], r12
0x180004a3f  lea     rax, [rsp+98h+var_34]
0x180004a44  mov     [rsp+98h+var_60], rax
0x180004a49  mov     [rsp+98h+var_68], r12
0x180004a4e  mov     dword ptr [rsp+98h+var_70], r12d
0x180004a53  mov     [rsp+98h+var_78], 1
0x180004a5b  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180004a60  test    eax, eax
0x180004a62  js      loc_180004B2B
0x180004a68  or      dword ptr [rbx+4], 20h
0x180004a6c  and     esi, 20h
0x180004a6f  mov     rcx, [rbp+328h]
0x180004a76  test    rcx, rcx
0x180004a79  jz      short loc_180004A8B
0x180004a7b  cmp     [rsp+98h+var_38], 1
0x180004a80  jnz     short loc_180004A8B
0x180004a82  mov     rax, [rcx]
0x180004a85  mov     rax, [rax+50h]
0x180004a89  jmp     short loc_180004A99
0x180004a8b  mov     rcx, [rbp+20h]
0x180004a8f  mov     rax, [rcx]
0x180004a92  mov     rax, [rax+0C8h]
0x180004a99  mov     edx, [rsp+98h+arg_20]
0x180004aa0  mov     r9, rbx
0x180004aa3  mov     [rsp+98h+var_70], rdi
0x180004aa8  mov     r8, r14
0x180004aab  mov     [rsp+98h+var_78], edx
0x180004aaf  mov     edx, [rsp+98h+arg_18]
0x180004ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abb  mov     edx, [rbx+4]
0x180004abe  mov     ecx, edx
0x180004ac0  test    esi, esi
0x180004ac2  jnz     short loc_180004ACA
0x180004ac4  and     ecx, 0FFFFFFDFh
0x180004ac7  mov     [rbx+4], ecx
0x180004aca  test    eax, eax
0x180004acc  js      short loc_180004B2B
0x180004ace  test    cl, 4
0x180004ad1  jz      short loc_180004B2B
0x180004ad3  cmp     [rsp+98h+var_34], r12d
0x180004ad8  jnz     short loc_180004AE1
0x180004ada  mov     eax, 80070005h
0x180004adf  jmp     short loc_180004AFB
0x180004ae1  test    dl, 20h
0x180004ae4  jz      short loc_180004B2B
0x180004ae6  mov     r9, rbx; struct _METADATA_RECORD *
0x180004ae9  mov     r8, r14; unsigned __int16 *
0x180004aec  mov     edx, r15d; unsigned int
0x180004aef  mov     rcx, rbp; this
0x180004af2  call    ?IsReadAccessGranted@CADMCOMW@@QEAAJKPEBGPEAU_METADATA_RECORD@@@Z; CADMCOMW::IsReadAccessGranted(ulong,ushort const *,_METADATA_RECORD *)
0x180004af7  test    eax, eax
0x180004af9  jns     short loc_180004B2B
0x180004afb  test    rdi, rdi
0x180004afe  jz      short loc_180004B03
0x180004b00  mov     [rdi], r12d
0x180004b03  mov     rcx, [rbx+18h]
0x180004b07  test    rcx, rcx
0x180004b0a  jz      short loc_180004B20
0x180004b0c  mov     edx, [rbx+10h]
0x180004b0f  test    rdx, rdx
0x180004b12  jz      short loc_180004B20
0x180004b14  mov     [rcx], r12b
0x180004b17  inc     rcx
0x180004b1a  sub     rdx, 1
0x180004b1e  jnz     short loc_180004B14
0x180004b20  mov     [rbx+10h], r12d
0x180004b24  jmp     short loc_180004B2B
0x180004b26  mov     eax, 80070057h
0x180004b2b  lea     r11, [rsp+98h+var_28]
0x180004b30  mov     rbx, [r11+30h]
0x180004b34  mov     rbp, [r11+38h]
0x180004b38  mov     rsp, r11
0x180004b3b  pop     r15
0x180004b3d  pop     r14
0x180004b3f  pop     r12
0x180004b41  pop     rdi
0x180004b42  pop     rsi
0x180004b43  retn
```
