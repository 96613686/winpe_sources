# WSTContextTableInsertExNoLock(_RTL_GENERIC_TABLE *,unsigned __int64,_WST_CONTEXT *)

- ea: `0x18000cd24`
- end: `0x18000d03d`
- name: `?WSTContextTableInsertExNoLock@@YAJPEAU_RTL_GENERIC_TABLE@@_KPEAU_WST_CONTEXT@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(PRTL_GENERIC_TABLE Table, unsigned __int64, struct _WST_CONTEXT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cc6c`
- `0x180017b60`
- `0x18001d024`

## callees

- `0x18000ca08`
- `0x18000cd24`
- `0x18000ec70`
- `0x18001d544`

## import_xrefs

- `ntdll!RtlInsertElementGenericTable` at `0x18000cdb8`
- `ntdll!RtlInsertElementGenericTable` at `0x18000cff6`
- `ntdll!RtlInsertElementGenericTable` at `0x18000cdb8`
- `ntdll!RtlInsertElementGenericTable` at `0x18000cff6`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000cfc4`
- `ntdll!RtlDeleteElementGenericTable` at `0x18000cfc4`

## pseudocode

```c
__int64 __fastcall WSTContextTableInsertExNoLock(
        PRTL_GENERIC_TABLE Table,
        struct _WST_CONTEXT *a2,
        struct _WST_CONTEXT *a3)
{
  struct _WST_CONTEXT **inserted; // rax
  struct _WST_CONTEXT **v7; // rbx
  struct _WST_CONTEXT *v8; // rsi
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  unsigned __int64 v12; // rax
  __int64 v13; // r8
  unsigned __int64 v14; // rax
  __int64 result; // rax
  _QWORD Buffer[2]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 NewElement; // [rsp+90h] [rbp+18h] BYREF

  Buffer[1] = 0;
  NewElement = 0;
  Buffer[0] = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qqDDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (char)a3,
      *(_DWORD *)(*((_QWORD *)a3 + 3) + 44LL),
      *(_DWORD *)(*((_QWORD *)a3 + 3) + 40LL),
      (__int64)a3 + 168);
  inserted = (struct _WST_CONTEXT **)RtlInsertElementGenericTable(Table, Buffer, 0x10u, &NewElement);
  v7 = inserted;
  if ( inserted )
  {
    if ( NewElement )
      goto LABEL_50;
    v8 = *inserted;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_qqDDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (char)v8,
        *(_DWORD *)(*((_QWORD *)v8 + 3) + 44LL),
        *(_DWORD *)(*((_QWORD *)v8 + 3) + 40LL),
        (__int64)v8 + 168);
    if ( !*((_DWORD *)a3 + 65) )
    {
      v9 = *((_DWORD *)v8 + 65);
      if ( v9 )
      {
        if ( (v10 = *((_DWORD *)v8 + 55), v10 == -799211514)
          || v10 == -799211518
          || v10 == -805305464
          || v10 == -805305820
          || (v11 = 280609, (unsigned int)(v10 + 805306273) <= 0x12) && _bittest(&v11, v10 + 805306273)
          || v10 == -805306334
          || v10 == -1067646970
          || (unsigned int)(v10 + 1067646974) <= 2
          || v10 == -1073740755
          || v10 == -1073740920
          || v10 == -1073741276
          || (unsigned int)(v10 + 1073741729) <= 0x12 && _bittest(&v11, v10 + 1073741729)
          || v10 == -1073741790
          || v10 == -2146892959
          || v10 == -2146892976
          || v10 == -2146893042
          || v10 == -2146893044
          || v10 == -2147022654
          || v10 == -2147022959
          || v10 == -2147022989
          || v10 == -2147023566
          || (v12 = (unsigned int)(v10 + 2147023631), v13 = 0x2010800000000081LL, (unsigned int)v12 <= 0x3D)
          && _bittest64(&v13, v12)
          || v10 == -2147024810
          || v10 == -2147024891
          || v10 == 2242
          || v10 == 1937
          || v10 == 1907
          || v10 == 1330
          || (v14 = (unsigned int)(v10 - 1265), (unsigned int)v14 <= 0x3D) && _bittest64(&v13, v14)
          || v10 == 86
          || v10 == 5 )
        {
          *((_DWORD *)a3 + 65) = v9;
        }
      }
    }
    if ( !RtlDeleteElementGenericTable(Table, Buffer) )
      goto LABEL_50;
    _InterlockedCompareExchange((volatile signed __int32 *)v8 + 4, 0, 1);
    WSTDereferenceContext(v8);
    v7 = (struct _WST_CONTEXT **)RtlInsertElementGenericTable(Table, Buffer, 0x10u, &NewElement);
  }
  if ( v7 )
  {
LABEL_50:
    _InterlockedCompareExchange((volatile signed __int32 *)*v7 + 4, 1, 0);
    WSTReferenceContext(*v7);
    result = 0;
    v7[1] = a2;
    return result;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x18000cd24  mov     r11, rsp
0x18000cd27  mov     [r11+8], rbx
0x18000cd2b  mov     [r11+10h], rbp
0x18000cd2f  push    rsi
0x18000cd30  push    rdi
0x18000cd31  push    r12
0x18000cd33  push    r13
0x18000cd35  push    r14
0x18000cd37  sub     rsp, 50h
0x18000cd3b  mov     rdi, r8
0x18000cd3e  mov     qword ptr [r11-30h], 0
0x18000cd46  mov     r14, rdx
0x18000cd49  mov     byte ptr [r11+18h], 0
0x18000cd4e  mov     rbp, rcx
0x18000cd51  mov     [r11-38h], r8
0x18000cd55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd5c  lea     r12, WPP_GLOBAL_Control
0x18000cd63  cmp     rcx, r12
0x18000cd66  jz      short loc_18000CDA2
0x18000cd68  test    byte ptr [rcx+1Ch], 2
0x18000cd6c  jz      short loc_18000CDA2
0x18000cd6e  mov     r8, [r8+18h]
0x18000cd72  lea     rax, [rdi+0A8h]
0x18000cd79  mov     rcx, [rcx+10h]; LoggerHandle
0x18000cd7d  mov     edx, 0Ah
0x18000cd82  mov     [r11-40h], rax
0x18000cd86  mov     r9, rbp
0x18000cd89  mov     eax, [r8+28h]
0x18000cd8d  mov     dword ptr [rsp+78h+var_48], eax; char
0x18000cd91  mov     eax, [r8+2Ch]
0x18000cd95  mov     dword ptr [rsp+78h+var_50], eax; char
0x18000cd99  mov     [r11-58h], rdi
0x18000cd9d  call    WPP_SF_qqDDZ
0x18000cda2  lea     r9, [rsp+78h+NewElement]; NewElement
0x18000cdaa  mov     r8d, 10h; BufferSize
0x18000cdb0  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000cdb5  mov     rcx, rbp; Table
0x18000cdb8  call    cs:__imp_RtlInsertElementGenericTable
0x18000cdbe  mov     rbx, rax
0x18000cdc1  mov     r13d, 1
0x18000cdc7  test    rax, rax
0x18000cdca  jz      loc_18000CFFF
0x18000cdd0  cmp     [rsp+78h+NewElement], 0
0x18000cdd8  jnz     loc_18000D004
0x18000cdde  mov     rsi, [rax]
0x18000cde1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cde8  cmp     rcx, r12
0x18000cdeb  jz      short loc_18000CE28
0x18000cded  test    byte ptr [rcx+1Ch], 2
0x18000cdf1  jz      short loc_18000CE28
0x18000cdf3  mov     r8, [rsi+18h]
0x18000cdf7  lea     rax, [rsi+0A8h]
0x18000cdfe  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ce02  lea     edx, [r13+0Ah]
0x18000ce06  mov     [rsp+78h+var_40], rax; __int64
0x18000ce0b  mov     r9, rbp
0x18000ce0e  mov     eax, [r8+28h]
0x18000ce12  mov     dword ptr [rsp+78h+var_48], eax; char
0x18000ce16  mov     eax, [r8+2Ch]
0x18000ce1a  mov     dword ptr [rsp+78h+var_50], eax; char
0x18000ce1e  mov     qword ptr [rsp+78h+var_58], rsi; char
0x18000ce23  call    WPP_SF_qqDDZ
0x18000ce28  cmp     dword ptr [rdi+104h], 0
0x18000ce2f  jnz     loc_18000CFBC
0x18000ce35  mov     edx, [rsi+104h]
0x18000ce3b  test    edx, edx
0x18000ce3d  jz      loc_18000CFBC
0x18000ce43  mov     ecx, [rsi+0DCh]
0x18000ce49  cmp     ecx, 0D05D0006h
0x18000ce4f  jz      loc_18000CFB6
0x18000ce55  cmp     ecx, 0D05D0002h
0x18000ce5b  jz      loc_18000CFB6
0x18000ce61  cmp     ecx, 0D0000388h
0x18000ce67  jz      loc_18000CFB6
0x18000ce6d  cmp     ecx, 0D0000224h
0x18000ce73  jz      loc_18000CFB6
0x18000ce79  lea     eax, [rcx+2FFFFFA1h]
0x18000ce7f  mov     r8d, 44821h
0x18000ce85  cmp     eax, 12h
0x18000ce88  ja      short loc_18000CE94
0x18000ce8a  bt      r8d, eax
0x18000ce8e  jb      loc_18000CFB6
0x18000ce94  cmp     ecx, 0D0000022h
0x18000ce9a  jz      loc_18000CFB6
0x18000cea0  cmp     ecx, 0C05D0006h
0x18000cea6  jz      loc_18000CFB6
0x18000ceac  lea     eax, [rcx+3FA2FFFEh]
0x18000ceb2  cmp     eax, 2
0x18000ceb5  jbe     loc_18000CFB6
0x18000cebb  cmp     ecx, 0C000042Dh
0x18000cec1  jz      loc_18000CFB6
0x18000cec7  cmp     ecx, 0C0000388h
0x18000cecd  jz      loc_18000CFB6
0x18000ced3  cmp     ecx, 0C0000224h
0x18000ced9  jz      loc_18000CFB6
0x18000cedf  lea     eax, [rcx+3FFFFFA1h]
0x18000cee5  cmp     eax, 12h
0x18000cee8  ja      short loc_18000CEF4
0x18000ceea  bt      r8d, eax
0x18000ceee  jb      loc_18000CFB6
0x18000cef4  cmp     ecx, 0C0000022h
0x18000cefa  jz      loc_18000CFB6
0x18000cf00  cmp     ecx, 80090361h
0x18000cf06  jz      loc_18000CFB6
0x18000cf0c  cmp     ecx, 80090350h
0x18000cf12  jz      loc_18000CFB6
0x18000cf18  cmp     ecx, 8009030Eh
0x18000cf1e  jz      loc_18000CFB6
0x18000cf24  cmp     ecx, 8009030Ch
0x18000cf2a  jz      loc_18000CFB6
0x18000cf30  cmp     ecx, 800708C2h
0x18000cf36  jz      short loc_18000CFB6
0x18000cf38  cmp     ecx, 80070791h
0x18000cf3e  jz      short loc_18000CFB6
0x18000cf40  cmp     ecx, 80070773h
0x18000cf46  jz      short loc_18000CFB6
0x18000cf48  cmp     ecx, 80070532h
0x18000cf4e  jz      short loc_18000CFB6
0x18000cf50  lea     eax, [rcx+7FF8FB0Fh]
0x18000cf56  mov     r8, 2010800000000081h
0x18000cf60  cmp     eax, 3Dh ; '='
0x18000cf63  ja      short loc_18000CF6B
0x18000cf65  bt      r8, rax
0x18000cf69  jb      short loc_18000CFB6
0x18000cf6b  cmp     ecx, 80070056h
0x18000cf71  jz      short loc_18000CFB6
0x18000cf73  cmp     ecx, 80070005h
0x18000cf79  jz      short loc_18000CFB6
0x18000cf7b  cmp     ecx, 8C2h
0x18000cf81  jz      short loc_18000CFB6
0x18000cf83  cmp     ecx, 791h
0x18000cf89  jz      short loc_18000CFB6
0x18000cf8b  cmp     ecx, 773h
0x18000cf91  jz      short loc_18000CFB6
0x18000cf93  cmp     ecx, 532h
0x18000cf99  jz      short loc_18000CFB6
0x18000cf9b  lea     eax, [rcx-4F1h]
0x18000cfa1  cmp     eax, 3Dh ; '='
0x18000cfa4  ja      short loc_18000CFAC
0x18000cfa6  bt      r8, rax
0x18000cfaa  jb      short loc_18000CFB6
0x18000cfac  cmp     ecx, 56h ; 'V'
0x18000cfaf  jz      short loc_18000CFB6
0x18000cfb1  cmp     ecx, 5
0x18000cfb4  jnz     short loc_18000CFBC
0x18000cfb6  mov     [rdi+104h], edx
0x18000cfbc  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000cfc1  mov     rcx, rbp; Table
0x18000cfc4  call    cs:__imp_RtlDeleteElementGenericTable
0x18000cfca  test    al, al
0x18000cfcc  jz      short loc_18000D004
0x18000cfce  xor     edx, edx
0x18000cfd0  mov     eax, r13d
0x18000cfd3  lock cmpxchg [rsi+10h], edx
0x18000cfd8  mov     rcx, rsi; struct _WST_CONTEXT *
0x18000cfdb  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18000cfe0  lea     r9, [rsp+78h+NewElement]; NewElement
0x18000cfe8  mov     r8d, 10h; BufferSize
0x18000cfee  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000cff3  mov     rcx, rbp; Table
0x18000cff6  call    cs:__imp_RtlInsertElementGenericTable
0x18000cffc  mov     rbx, rax
0x18000cfff  test    rbx, rbx
0x18000d002  jz      short loc_18000D01F
0x18000d004  mov     rcx, [rbx]
0x18000d007  xor     eax, eax
0x18000d009  lock cmpxchg [rcx+10h], r13d
0x18000d00f  mov     rcx, [rbx]; struct _WST_CONTEXT *
0x18000d012  call    ?WSTReferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTReferenceContext(_WST_CONTEXT *)
0x18000d017  xor     eax, eax
0x18000d019  mov     [rbx+8], r14
0x18000d01d  jmp     short loc_18000D024
0x18000d01f  mov     eax, 0C000009Ah
0x18000d024  lea     r11, [rsp+78h+var_28]
0x18000d029  mov     rbx, [r11+30h]
0x18000d02d  mov     rbp, [r11+38h]
0x18000d031  mov     rsp, r11
0x18000d034  pop     r14
0x18000d036  pop     r13
0x18000d038  pop     r12
0x18000d03a  pop     rdi
0x18000d03b  pop     rsi
0x18000d03c  retn
```
