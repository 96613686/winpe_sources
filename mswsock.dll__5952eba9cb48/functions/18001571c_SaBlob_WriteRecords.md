# SaBlob_WriteRecords

- ea: `0x18001571c`
- end: `0x18001595b`
- name: `SaBlob_WriteRecords`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015310`

## callees

- `0x18001571c`
- `0x1800164fc`
- `0x18001671c`
- `0x180020c40`
- `0x180022bd2`
- `0x180029a14`
- `0x1800380b0`
- `0x18003ad7c`
- `0x18003ae8c`

## import_xrefs

- `DNSAPI!DnsAddrBuildFromDnsRecord` at `0x180015831`
- `DNSAPI!DnsAddrBuildFromDnsRecord` at `0x180015831`

## string_xrefs

- `0x18001593d`: `SaBlob after WriteRecords():`

## pseudocode

```c
__int64 __fastcall SaBlob_WriteRecords(_QWORD *a1, __int64 *a2)
{
  unsigned int v4; // edi
  int v5; // r15d
  int v6; // esi
  __int64 v7; // rcx
  _WORD *v8; // rdx
  BOOL v9; // r8d
  DWORD v10; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  _WORD *v12; // rdx
  _WORD v14[2]; // [rsp+30h] [rbp-40h] BYREF
  int v15; // [rsp+34h] [rbp-3Ch]
  int v16; // [rsp+38h] [rbp-38h]
  __int64 v17; // [rsp+3Ch] [rbp-34h]
  int v18; // [rsp+44h] [rbp-2Ch]
  int v19; // [rsp+48h] [rbp-28h]
  int v20; // [rsp+4Ch] [rbp-24h]
  int v21; // [rsp+50h] [rbp-20h]

  v4 = 0;
  memset_0(v14, 0, 0x40u);
  v5 = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qqd(1025, 15, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, a1, a2);
  while ( a2 )
  {
    if ( (*((_DWORD *)a2 + 5) & 3u) >= 2 )
      goto LABEL_35;
    v6 = *((unsigned __int16 *)a2 + 8);
    v7 = (unsigned int)(v6 - 1);
    if ( v6 != 1 )
    {
      if ( v6 == 5 )
      {
        v8 = (_WORD *)a2[1];
        v9 = 1;
        goto LABEL_14;
      }
      if ( v6 == 12 )
      {
        v8 = (_WORD *)a2[4];
        v9 = *a1 != 0;
LABEL_14:
        v10 = SaBlob_WriteNameOrAlias((__int64)a1, v8, v9);
LABEL_31:
        v4 = v10;
        goto LABEL_32;
      }
      v7 = (unsigned int)(v6 - 28);
      if ( v6 != 28 && v6 != 34 )
      {
        if ( (xmmword_180063D60 & 0x10) != 0 )
          WPP_SF_d(1028, 16, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, *((unsigned __int16 *)a2 + 8));
        v4 = 13;
LABEL_33:
        if ( (xmmword_180063D60 & 0x10) != 0 )
          WPP_SF_qdd(1028, 17, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, a2, v6, v4);
        goto LABEL_35;
      }
    }
    if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline(v7, 28, 2);
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( (_WORD)v6 == 1 )
      {
        v14[0] = 2;
        v15 = *((_DWORD *)a2 + 8);
        v21 = 16;
      }
      else if ( (_WORD)v6 == 28 )
      {
        v14[0] = 23;
        v19 = *((unsigned __int16 *)a2 + 15);
        v16 = *((_DWORD *)a2 + 8);
        v17 = *(__int64 *)((char *)a2 + 36);
        v18 = *((_DWORD *)a2 + 11);
        v21 = 28;
      }
      else if ( v6 == 34 )
      {
        v21 = 28;
        v14[0] = 22;
        v15 = *((unsigned __int8 *)a2 + 32);
        v16 = 20;
        v17 = *(__int64 *)((char *)a2 + 33);
        v18 = *(_DWORD *)((char *)a2 + 41);
        v19 = *(_DWORD *)((char *)a2 + 45);
        v20 = *(_DWORD *)((char *)a2 + 49);
      }
    }
    else
    {
      DnsAddrBuildFromDnsRecord(v14, a2, 2);
    }
    v4 = SaBlob_WriteAddress((__int64)a1, v14);
    if ( !v5 && !*a1 )
    {
      v12 = (_WORD *)a2[1];
      if ( v12 )
      {
        v10 = SaBlob_WriteNameOrAlias((__int64)a1, v12, 0);
        v5 = 1;
        goto LABEL_31;
      }
    }
LABEL_32:
    if ( v4 )
      goto LABEL_33;
LABEL_35:
    a2 = (__int64 *)*a2;
  }
  Print_SaBlob("SaBlob after WriteRecords():", a1);
  return v4;
}

```

## disassembly

```asm
0x18001571c  push    rbp
0x18001571e  push    rbx
0x18001571f  push    rsi
0x180015720  push    rdi
0x180015721  push    r13
0x180015723  push    r14
0x180015725  push    r15
0x180015727  mov     rbp, rsp
0x18001572a  sub     rsp, 70h
0x18001572e  mov     rbx, rdx
0x180015731  mov     r14, rcx
0x180015734  xor     edi, edi
0x180015736  lea     rcx, [rbp+var_40]; void *
0x18001573a  xor     edx, edx; Val
0x18001573c  lea     r8d, [rdi+40h]; Size
0x180015740  call    memset_0
0x180015745  xor     r15d, r15d
0x180015748  lea     r8d, [rdi+2]
0x18001574c  test    byte ptr cs:xmmword_180063D60, r8b
0x180015753  lea     r13d, [rdi+1]
0x180015757  jz      short loc_18001577E
0x180015759  lea     edx, [rdi+0Fh]
0x18001575c  mov     [rsp+70h+var_48], r13d
0x180015761  mov     ecx, 401h
0x180015766  mov     [rsp+70h+var_50], rbx
0x18001576b  mov     r9, r14
0x18001576e  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x180015775  call    WPP_SF_qqd
0x18001577a  lea     r8d, [rdi+2]
0x18001577e  test    rbx, rbx
0x180015781  jz      loc_18001593A
0x180015787  mov     edx, 1Ch
0x18001578c  mov     eax, [rbx+14h]
0x18001578f  and     al, 3
0x180015791  cmp     al, r8b
0x180015794  jnb     loc_18001592E
0x18001579a  movzx   esi, word ptr [rbx+10h]
0x18001579e  mov     ecx, esi
0x1800157a0  sub     ecx, r13d
0x1800157a3  jz      short loc_180015809
0x1800157a5  sub     ecx, 4
0x1800157a8  jz      short loc_180015800
0x1800157aa  sub     ecx, 7
0x1800157ad  jz      short loc_1800157E5
0x1800157af  sub     ecx, 10h
0x1800157b2  jz      short loc_180015809
0x1800157b4  cmp     ecx, 6
0x1800157b7  jz      short loc_180015809
0x1800157b9  test    byte ptr cs:xmmword_180063D60, 10h
0x1800157c0  jz      short loc_1800157DB
0x1800157c2  mov     edx, 10h
0x1800157c7  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x1800157ce  mov     ecx, 404h
0x1800157d3  mov     r9d, esi
0x1800157d6  call    WPP_SF_d
0x1800157db  mov     edi, 0Dh
0x1800157e0  jmp     loc_1800158FB
0x1800157e5  mov     rdx, [rbx+20h]
0x1800157e9  xor     r8d, r8d
0x1800157ec  cmp     [r14], r8
0x1800157ef  setnz   r8b
0x1800157f3  mov     rcx, r14
0x1800157f6  call    SaBlob_WriteNameOrAlias
0x1800157fb  jmp     loc_1800158F5
0x180015800  mov     rdx, [rbx+8]
0x180015804  mov     r8d, r13d
0x180015807  jmp     short loc_1800157F3
0x180015809  mov     eax, cs:Feature_5977_1413__private_featureState
0x18001580f  test    al, 10h
0x180015811  jz      short loc_180015818
0x180015813  and     eax, r13d
0x180015816  jmp     short loc_180015826
0x180015818  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x18001581d  mov     edx, 1Ch
0x180015822  lea     r8d, [rdx-1Ah]
0x180015826  test    eax, eax
0x180015828  jnz     short loc_180015842
0x18001582a  mov     rdx, rbx
0x18001582d  lea     rcx, [rbp+var_40]
0x180015831  call    cs:__imp_DnsAddrBuildFromDnsRecord
0x180015838  nop     dword ptr [rax+rax+00h]
0x18001583d  jmp     loc_1800158C5
0x180015842  cmp     si, r13w
0x180015846  jnz     short loc_18001585C
0x180015848  mov     [rbp+var_40], r8w
0x18001584d  mov     eax, [rbx+20h]
0x180015850  mov     [rbp+var_3C], eax
0x180015853  mov     [rbp+var_20], 10h
0x18001585a  jmp     short loc_1800158C5
0x18001585c  cmp     si, dx
0x18001585f  jnz     short loc_18001588C
0x180015861  mov     eax, 17h
0x180015866  mov     [rbp+var_40], ax
0x18001586a  movzx   eax, word ptr [rbx+1Eh]
0x18001586e  mov     [rbp+var_28], eax
0x180015871  mov     eax, [rbx+20h]
0x180015874  mov     [rbp+var_38], eax
0x180015877  movsd   xmm0, qword ptr [rbx+24h]
0x18001587c  movsd   [rbp+var_34], xmm0
0x180015881  mov     eax, [rbx+2Ch]
0x180015884  mov     [rbp+var_2C], eax
0x180015887  mov     [rbp+var_20], edx
0x18001588a  jmp     short loc_1800158C5
0x18001588c  cmp     esi, 22h ; '"'
0x18001588f  jnz     short loc_1800158C5
0x180015891  mov     [rbp+var_20], edx
0x180015894  lea     eax, [rsi-0Ch]
0x180015897  mov     [rbp+var_40], ax
0x18001589b  movzx   eax, byte ptr [rbx+20h]
0x18001589f  mov     [rbp+var_3C], eax
0x1800158a2  mov     [rbp+var_38], 14h
0x1800158a9  movsd   xmm0, qword ptr [rbx+21h]
0x1800158ae  movsd   [rbp+var_34], xmm0
0x1800158b3  mov     eax, [rbx+29h]
0x1800158b6  mov     [rbp+var_2C], eax
0x1800158b9  mov     eax, [rbx+2Dh]
0x1800158bc  mov     [rbp+var_28], eax
0x1800158bf  mov     eax, [rbx+31h]
0x1800158c2  mov     [rbp+var_24], eax
0x1800158c5  lea     rdx, [rbp+var_40]
0x1800158c9  mov     rcx, r14
0x1800158cc  call    SaBlob_WriteAddress
0x1800158d1  mov     edi, eax
0x1800158d3  test    r15d, r15d
0x1800158d6  jnz     short loc_1800158F7
0x1800158d8  cmp     qword ptr [r14], 0
0x1800158dc  jnz     short loc_1800158F7
0x1800158de  mov     rdx, [rbx+8]
0x1800158e2  test    rdx, rdx
0x1800158e5  jz      short loc_1800158F7
0x1800158e7  xor     r8d, r8d
0x1800158ea  mov     rcx, r14
0x1800158ed  call    SaBlob_WriteNameOrAlias
0x1800158f2  mov     r15d, r13d
0x1800158f5  mov     edi, eax
0x1800158f7  test    edi, edi
0x1800158f9  jz      short loc_180015925
0x1800158fb  test    byte ptr cs:xmmword_180063D60, 10h
0x180015902  jz      short loc_180015925
0x180015904  mov     edx, 11h
0x180015909  mov     [rsp+70h+var_48], edi
0x18001590d  mov     ecx, 404h
0x180015912  mov     dword ptr [rsp+70h+var_50], esi
0x180015916  mov     r9, rbx
0x180015919  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x180015920  call    WPP_SF_qdd
0x180015925  mov     edx, 1Ch
0x18001592a  lea     r8d, [rdx-1Ah]
0x18001592e  mov     rbx, [rbx]
0x180015931  test    rbx, rbx
0x180015934  jnz     loc_18001578C
0x18001593a  mov     rdx, r14
0x18001593d  lea     rcx, aSablobAfterWri; "SaBlob after WriteRecords():"
0x180015944  call    Print_SaBlob
0x180015949  mov     eax, edi
0x18001594b  add     rsp, 70h
0x18001594f  pop     r15
0x180015951  pop     r14
0x180015953  pop     r13
0x180015955  pop     rdi
0x180015956  pop     rsi
0x180015957  pop     rbx
0x180015958  pop     rbp
0x180015959  retn
```
