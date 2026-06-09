# KerbUnpackData(uchar *,ulong,ulong,void * *)

- ea: `0x1800160e0`
- end: `0x180016352`
- name: `?KerbUnpackData@@YAJPEAEKKPEAPEAX@Z`
- size: `626`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int, void **)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001bf0`
- `0x1800041f0`
- `0x18000d220`
- `0x18000ed70`
- `0x18001cc90`
- `0x18002fcd0`
- `0x180030be0`
- `0x18003185c`
- `0x180031968`
- `0x1800355cc`
- `0x180035dc0`

## callees

- `0x1800160e0`
- `0x180023cb8`
- `0x180023ce0`

## import_xrefs

- `MSASN1!ASN1_CreateDecoder` at `0x18001619b`
- `MSASN1!ASN1_CreateDecoder` at `0x18001619b`
- `MSASN1!ASN1_CloseDecoder` at `0x1800162f8`
- `MSASN1!ASN1_CloseDecoder` at `0x1800162f8`
- `MSASN1!ASN1_CreateModule` at `0x180016172`
- `MSASN1!ASN1_CreateModule` at `0x180016172`
- `MSASN1!ASN1_Decode` at `0x180016237`
- `MSASN1!ASN1_Decode` at `0x180016237`

## pseudocode

```c
__int64 __fastcall KerbUnpackData(unsigned __int8 *a1, int a2, unsigned int a3, void **a4)
{
  __int64 Module; // rax
  unsigned int Decoder; // eax
  PVOID *v10; // rcx
  unsigned int v11; // r14d
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  _QWORD v17[9]; // [rsp+50h] [rbp-48h] BYREF

  v17[0] = 0;
  if ( !a2 || !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
    return 60;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = PKU2UMSG_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               49,
               off_180047350,
               off_1800471C0,
               off_180047030,
               qword_180049F80,
               846556016);
    PKU2UMSG_Module = Module;
  }
  Decoder = ASN1_CreateDecoder(Module, v17, 0, 0, 0);
  if ( Decoder )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, Decoder);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
      {
        v11 = 60;
        WPP_SF_d(v10[2], 80, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, 60);
        return v11;
      }
    }
    return 60;
  }
  v12 = v17[0];
  v11 = 0;
  *a4 = 0;
  v13 = ASN1_Decode(v12, a4, a3, 8, a1, a2);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
        (unsigned int)v13);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 == -1009 || v14 == -1002 )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
        WPP_SF_d(v15[2], 82, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, a3);
      v11 = -2147483647;
    }
    else
    {
      if ( v14 != -1011 && v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        WPP_SF_d(v15[2], 83, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids, v14);
      v11 = 60;
    }
    *a4 = 0;
  }
  if ( v17[0] )
  {
    ASN1_CloseDecoder();
    return v11;
  }
  return v11;
}

```

## disassembly

```asm
0x1800160e0  push    rbx
0x1800160e2  push    rbp
0x1800160e3  push    rsi
0x1800160e4  push    rdi
0x1800160e5  push    r14
0x1800160e7  push    r15
0x1800160e9  sub     rsp, 68h
0x1800160ed  xor     r15d, r15d
0x1800160f0  mov     rsi, r9
0x1800160f3  mov     [rsp+98h+var_48], r15
0x1800160f8  mov     ebp, r8d
0x1800160fb  mov     edi, edx
0x1800160fd  mov     rbx, rcx
0x180016100  test    edx, edx
0x180016102  jz      loc_18001630E
0x180016108  test    rcx, rcx
0x18001610b  jz      loc_18001630E
0x180016111  cmp     cs:?fKRB5ModuleStarted@@3HA, r15d; int fKRB5ModuleStarted
0x180016118  jnz     short loc_180016181
0x18001611a  mov     [rsp+98h+var_58], 32756B70h
0x180016122  lea     rax, qword_180049F80
0x180016129  mov     [rsp+98h+var_60], rax
0x18001612e  mov     edx, 400h
0x180016133  lea     rax, off_180047030
0x18001613a  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180016144  mov     [rsp+98h+var_68], rax
0x180016149  mov     ecx, 10000h
0x18001614e  lea     rax, off_1800471C0
0x180016155  mov     r9d, 31h ; '1'
0x18001615b  mov     [rsp+98h+var_70], rax
0x180016160  mov     r8d, 1000h
0x180016166  lea     rax, off_180047350
0x18001616d  mov     [rsp+98h+var_78], rax
0x180016172  call    cs:__imp_ASN1_CreateModule
0x180016178  mov     cs:PKU2UMSG_Module, rax
0x18001617f  jmp     short loc_180016188
0x180016181  mov     rax, cs:PKU2UMSG_Module
0x180016188  xor     r9d, r9d
0x18001618b  mov     [rsp+98h+var_78], r15
0x180016190  xor     r8d, r8d
0x180016193  lea     rdx, [rsp+98h+var_48]
0x180016198  mov     rcx, rax
0x18001619b  call    cs:__imp_ASN1_CreateDecoder
0x1800161a1  test    eax, eax
0x1800161a3  jz      short loc_180016217
0x1800161a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161ac  lea     rdi, WPP_GLOBAL_Control
0x1800161b3  cmp     rcx, rdi
0x1800161b6  jz      loc_18001633C
0x1800161bc  test    byte ptr [rcx+1Ch], 1
0x1800161c0  jz      short loc_1800161E1
0x1800161c2  mov     rcx, [rcx+10h]
0x1800161c6  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800161cd  mov     edx, 4Dh ; 'M'
0x1800161d2  mov     r9d, eax
0x1800161d5  call    WPP_SF_d
0x1800161da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161e1  cmp     rcx, rdi
0x1800161e4  jz      loc_18001633C
0x1800161ea  test    byte ptr [rcx+1Ch], 1
0x1800161ee  jz      loc_18001633C
0x1800161f4  mov     rcx, [rcx+10h]
0x1800161f8  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800161ff  mov     r14d, 3Ch ; '<'
0x180016205  mov     edx, 50h ; 'P'
0x18001620a  mov     r9d, r14d
0x18001620d  call    WPP_SF_d
0x180016212  jmp     loc_180016342
0x180016217  mov     rcx, [rsp+98h+var_48]
0x18001621c  mov     r9d, 8
0x180016222  mov     dword ptr [rsp+98h+var_70], edi
0x180016226  mov     r8d, ebp
0x180016229  mov     rdx, rsi
0x18001622c  mov     [rsp+98h+var_78], rbx
0x180016231  mov     r14d, r15d
0x180016234  mov     [rsi], r15
0x180016237  call    cs:__imp_ASN1_Decode
0x18001623d  mov     ebx, eax
0x18001623f  test    eax, eax
0x180016241  jns     loc_1800162EE
0x180016247  mov     rcx, cs:WPP_GLOBAL_Control
0x18001624e  lea     rdi, WPP_GLOBAL_Control
0x180016255  cmp     rcx, rdi
0x180016258  jz      short loc_18001627F
0x18001625a  test    byte ptr [rcx+1Ch], 4
0x18001625e  jz      short loc_18001627F
0x180016260  mov     rcx, [rcx+10h]
0x180016264  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18001626b  mov     edx, 51h ; 'Q'
0x180016270  mov     r9d, eax
0x180016273  call    WPP_SF_d
0x180016278  mov     rcx, cs:WPP_GLOBAL_Control
0x18001627f  cmp     ebx, 0FFFFFC0Fh
0x180016285  jz      short loc_1800162C2
0x180016287  cmp     ebx, 0FFFFFC16h
0x18001628d  jz      short loc_1800162C2
0x18001628f  cmp     ebx, 0FFFFFC0Dh
0x180016295  jz      short loc_1800162BA
0x180016297  cmp     rcx, rdi
0x18001629a  jz      short loc_1800162BA
0x18001629c  test    byte ptr [rcx+1Ch], 1
0x1800162a0  jz      short loc_1800162BA
0x1800162a2  mov     rcx, [rcx+10h]
0x1800162a6  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800162ad  mov     edx, 53h ; 'S'
0x1800162b2  mov     r9d, ebx
0x1800162b5  call    WPP_SF_d
0x1800162ba  mov     r14d, 3Ch ; '<'
0x1800162c0  jmp     short loc_1800162EB
0x1800162c2  cmp     rcx, rdi
0x1800162c5  jz      short loc_1800162E5
0x1800162c7  test    byte ptr [rcx+1Ch], 4
0x1800162cb  jz      short loc_1800162E5
0x1800162cd  mov     rcx, [rcx+10h]
0x1800162d1  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x1800162d8  mov     edx, 52h ; 'R'
0x1800162dd  mov     r9d, ebp
0x1800162e0  call    WPP_SF_d
0x1800162e5  mov     r14d, 80000001h
0x1800162eb  mov     [rsi], r15
0x1800162ee  mov     rcx, [rsp+98h+var_48]
0x1800162f3  test    rcx, rcx
0x1800162f6  jz      short loc_180016342
0x1800162f8  call    cs:__imp_ASN1_CloseDecoder
0x1800162fe  mov     eax, r14d
0x180016301  add     rsp, 68h
0x180016305  pop     r15
0x180016307  pop     r14
0x180016309  pop     rdi
0x18001630a  pop     rsi
0x18001630b  pop     rbp
0x18001630c  pop     rbx
0x18001630d  retn
0x18001630e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016315  lea     rdi, WPP_GLOBAL_Control
0x18001631c  cmp     rcx, rdi
0x18001631f  jz      short loc_18001633C
0x180016321  test    byte ptr [rcx+1Ch], 1
0x180016325  jz      short loc_18001633C
0x180016327  mov     rcx, [rcx+10h]
0x18001632b  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180016332  mov     edx, 4Fh ; 'O'
0x180016337  call    WPP_SF_
0x18001633c  mov     r14d, 3Ch ; '<'
0x180016342  mov     eax, r14d
0x180016345  add     rsp, 68h
0x180016349  pop     r15
0x18001634b  pop     r14
0x18001634d  pop     rdi
0x18001634e  pop     rsi
0x18001634f  pop     rbp
0x180016350  pop     rbx
0x180016351  retn
```
