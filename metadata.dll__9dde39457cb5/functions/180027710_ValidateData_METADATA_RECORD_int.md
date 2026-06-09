# ValidateData(_METADATA_RECORD *,int)

- ea: `0x180027710`
- end: `0x180027927`
- name: `?ValidateData@@YAJPEAU_METADATA_RECORD@@H@Z`
- size: `535`
- prototype: `__int64 __fastcall(struct _METADATA_RECORD *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800155dc`
- `0x180019d8c`

## callees

- `0x180027710`

## import_xrefs

- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800277a2`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1800277a2`

## pseudocode

```c
__int64 __fastcall ValidateData(struct _METADATA_RECORD *a1, int a2)
{
  unsigned __int8 *pbMDData; // r9
  DWORD *p_dwMDDataLen; // r8
  DWORD dwMDDataType; // ecx
  DWORD v7; // eax
  unsigned int v8; // edx
  ULONG v10; // r8d
  ULONG v11; // r8d
  __int64 v12; // r10
  unsigned int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r10
  unsigned int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // r8
  DWORD dwMDDataLen; // ecx
  DWORD v21; // ecx
  __int64 v22; // r8
  __int64 v23; // rcx
  unsigned int v24; // eax

  pbMDData = a1->pbMDData;
  p_dwMDDataLen = &a1->dwMDDataLen;
  if ( !pbMDData && *p_dwMDDataLen )
    return (unsigned int)-2147024809;
  dwMDDataType = a1->dwMDDataType;
  if ( dwMDDataType - 1 > 4 )
    return (unsigned int)-2147024809;
  if ( (a1->dwMDAttributes & 0xFFFFFF22) != 0 )
    return (unsigned int)-2147024809;
  v7 = a1->dwMDAttributes & 0x40;
  if ( (a1->dwMDAttributes & 8) != 0 )
  {
    if ( v7 )
      return (unsigned int)-2147024809;
  }
  if ( dwMDDataType == 1 )
  {
    if ( *p_dwMDDataLen != 4 )
      return (unsigned int)-2147024809;
  }
  else if ( dwMDDataType != 3 )
  {
    goto LABEL_13;
  }
  if ( v7 )
    return (unsigned int)-2147024809;
LABEL_13:
  if ( a1->dwMDIdentifier == 6027 )
  {
    if ( dwMDDataType == 3 && pbMDData && *p_dwMDDataLen )
      return RtlValidRelativeSecurityDescriptor(pbMDData, *p_dwMDDataLen, 3u) == 0 ? 0x8007053A : 0;
    else
      return (unsigned int)-2147023558;
  }
  else if ( dwMDDataType == 5 )
  {
    v10 = *p_dwMDDataLen;
    v8 = 0;
    if ( a2 )
    {
      if ( !v10 )
        return v8;
      if ( (v10 & 1) != 0 )
        return (unsigned int)-2147024809;
      v11 = v10 >> 1;
      if ( v11 == 1 )
        return (unsigned int)-2147024809;
      if ( *(_WORD *)&pbMDData[2 * v11 - 2] )
        return (unsigned int)-2147024809;
      v12 = v11 - 2;
      if ( *(_WORD *)&pbMDData[2 * v12] )
        return (unsigned int)-2147024809;
      if ( v11 != 2 )
      {
        v13 = 0;
        while ( v13 < (unsigned int)v12 )
        {
          v14 = v13;
          v15 = ++v13;
          if ( !*(_WORD *)&pbMDData[2 * v14] && !*(_WORD *)&pbMDData[2 * v15] )
            return (unsigned int)-2147024809;
        }
      }
    }
    else
    {
      if ( !v10 )
        return v8;
      if ( v10 == 1 )
        return (unsigned int)-2147024809;
      if ( pbMDData[v10 - 1] )
        return (unsigned int)-2147024809;
      v16 = v10 - 2;
      if ( pbMDData[v16] )
        return (unsigned int)-2147024809;
      if ( v10 != 2 )
      {
        v17 = 0;
        while ( v17 < (unsigned int)v16 )
        {
          v18 = v17;
          v19 = ++v17;
          if ( !pbMDData[v18] && !pbMDData[v19] )
            return (unsigned int)-2147024809;
        }
      }
    }
  }
  else if ( dwMDDataType == 2 || (v8 = 0, dwMDDataType == 4) )
  {
    dwMDDataLen = a1->dwMDDataLen;
    v8 = 0;
    if ( a2 )
    {
      if ( !dwMDDataLen )
        return v8;
      if ( (dwMDDataLen & 1) != 0 )
        return (unsigned int)-2147024809;
      v21 = dwMDDataLen >> 1;
      v22 = v21 - 1;
      if ( *(_WORD *)&pbMDData[2 * v22] )
        return (unsigned int)-2147024809;
      if ( v21 == 1 )
        return v8;
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)&pbMDData[2 * v23] );
    }
    else
    {
      if ( !dwMDDataLen )
        return v8;
      v22 = dwMDDataLen - 1;
      if ( pbMDData[v22] )
        return (unsigned int)-2147024809;
      if ( dwMDDataLen == 1 )
        return v8;
      v23 = -1;
      do
        ++v23;
      while ( pbMDData[v23] );
    }
    v24 = 0;
    if ( v23 != v22 )
      return (unsigned int)-2147024809;
    return v24;
  }
  return v8;
}

```

## disassembly

```asm
0x180027710  push    rbx
0x180027712  sub     rsp, 20h
0x180027716  mov     r9, [rcx+18h]
0x18002771a  lea     r8, [rcx+10h]
0x18002771e  xor     ebx, ebx
0x180027720  mov     r11d, edx
0x180027723  mov     r10, rcx
0x180027726  test    r9, r9
0x180027729  jnz     short loc_180027730
0x18002772b  cmp     [r8], ebx
0x18002772e  ja      short loc_180027762
0x180027730  mov     ecx, [rcx+0Ch]
0x180027733  lea     eax, [rcx-1]
0x180027736  cmp     eax, 4
0x180027739  ja      short loc_180027762
0x18002773b  test    dword ptr [r10+4], 0FFFFFF22h
0x180027743  jnz     short loc_180027762
0x180027745  mov     eax, [r10+4]
0x180027749  and     eax, 40h
0x18002774c  test    byte ptr [r10+4], 8
0x180027751  jz      short loc_180027757
0x180027753  test    eax, eax
0x180027755  jnz     short loc_180027762
0x180027757  cmp     ecx, 1
0x18002775a  jnz     short loc_18002776F
0x18002775c  cmp     dword ptr [r8], 4
0x180027760  jz      short loc_180027774
0x180027762  mov     edx, 80070057h
0x180027767  mov     eax, edx
0x180027769  add     rsp, 20h
0x18002776d  pop     rbx
0x18002776e  retn
0x18002776f  cmp     ecx, 3
0x180027772  jnz     short loc_180027778
0x180027774  test    eax, eax
0x180027776  jnz     short loc_180027762
0x180027778  cmp     dword ptr [r10], 178Bh
0x18002777f  jnz     short loc_1800277B7
0x180027781  cmp     ecx, 3
0x180027784  jz      short loc_18002778D
0x180027786  mov     edx, 8007053Ah
0x18002778b  jmp     short loc_180027767
0x18002778d  test    r9, r9
0x180027790  jz      short loc_180027786
0x180027792  mov     edx, [r8]; SecurityDescriptorLength
0x180027795  test    edx, edx
0x180027797  jz      short loc_180027786
0x180027799  mov     r8d, 3; RequiredInformation
0x18002779f  mov     rcx, r9; SecurityDescriptorInput
0x1800277a2  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800277a8  neg     al
0x1800277aa  mov     edx, 8007053Ah
0x1800277af  sbb     ecx, ecx
0x1800277b1  not     ecx
0x1800277b3  and     edx, ecx
0x1800277b5  jmp     short loc_180027767
0x1800277b7  cmp     ecx, 5
0x1800277ba  jnz     loc_18002788D
0x1800277c0  mov     r8d, [r8]
0x1800277c3  mov     edx, ebx
0x1800277c5  test    r11d, r11d
0x1800277c8  jz      short loc_18002782E
0x1800277ca  test    r8d, r8d
0x1800277cd  jz      short loc_180027767
0x1800277cf  test    r8b, 1
0x1800277d3  jnz     short loc_180027762
0x1800277d5  shr     r8d, 1
0x1800277d8  cmp     r8d, 1
0x1800277dc  jz      short loc_180027762
0x1800277de  lea     eax, [r8-1]
0x1800277e2  cmp     [r9+rax*2], bx
0x1800277e7  jnz     loc_180027762
0x1800277ed  lea     r10d, [r8-2]
0x1800277f1  cmp     [r9+r10*2], bx
0x1800277f6  jnz     loc_180027762
0x1800277fc  cmp     r8d, 2
0x180027800  jz      loc_180027767
0x180027806  mov     ecx, ebx
0x180027808  cmp     ecx, r10d
0x18002780b  jnb     loc_180027767
0x180027811  mov     eax, ecx
0x180027813  lea     r8d, [rcx+1]
0x180027817  mov     ecx, r8d
0x18002781a  cmp     [r9+rax*2], bx
0x18002781f  jnz     short loc_180027808
0x180027821  cmp     [r9+r8*2], bx
0x180027826  jz      loc_180027762
0x18002782c  jmp     short loc_180027808
0x18002782e  test    r8d, r8d
0x180027831  jz      loc_180027767
0x180027837  cmp     r8d, 1
0x18002783b  jz      loc_180027762
0x180027841  lea     eax, [r8-1]
0x180027845  cmp     [rax+r9], bl
0x180027849  jnz     loc_180027762
0x18002784f  lea     r10d, [r8-2]
0x180027853  cmp     [r10+r9], bl
0x180027857  jnz     loc_180027762
0x18002785d  cmp     r8d, 2
0x180027861  jz      loc_180027767
0x180027867  mov     ecx, ebx
0x180027869  cmp     ecx, r10d
0x18002786c  jnb     loc_180027767
0x180027872  mov     eax, ecx
0x180027874  lea     r8d, [rcx+1]
0x180027878  mov     ecx, r8d
0x18002787b  cmp     [rax+r9], bl
0x18002787f  jnz     short loc_180027869
0x180027881  cmp     [r8+r9], bl
0x180027885  jz      loc_180027762
0x18002788b  jmp     short loc_180027869
0x18002788d  cmp     ecx, 2
0x180027890  jz      short loc_18002789D
0x180027892  mov     edx, ebx
0x180027894  cmp     ecx, 4
0x180027897  jnz     loc_180027767
0x18002789d  mov     ecx, [r10+10h]
0x1800278a1  mov     edx, ebx
0x1800278a3  test    r11d, r11d
0x1800278a6  jz      short loc_1800278E5
0x1800278a8  test    ecx, ecx
0x1800278aa  jz      loc_180027767
0x1800278b0  test    cl, 1
0x1800278b3  jnz     loc_180027762
0x1800278b9  shr     ecx, 1
0x1800278bb  lea     eax, [rcx-1]
0x1800278be  mov     r8d, eax
0x1800278c1  cmp     [r9+rax*2], bx
0x1800278c6  jnz     loc_180027762
0x1800278cc  cmp     ecx, 1
0x1800278cf  jz      loc_180027767
0x1800278d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800278d9  inc     rcx
0x1800278dc  cmp     [r9+rcx*2], bx
0x1800278e1  jnz     short loc_1800278D9
0x1800278e3  jmp     short loc_180027913
0x1800278e5  test    ecx, ecx
0x1800278e7  jz      loc_180027767
0x1800278ed  lea     eax, [rcx-1]
0x1800278f0  mov     r8d, eax
0x1800278f3  cmp     [rax+r9], bl
0x1800278f7  jnz     loc_180027762
0x1800278fd  cmp     ecx, 1
0x180027900  jz      loc_180027767
0x180027906  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002790a  inc     rcx
0x18002790d  cmp     [r9+rcx], bl
0x180027911  jnz     short loc_18002790A
0x180027913  mov     edx, 80070057h
0x180027918  cmp     rcx, r8
0x18002791b  mov     eax, ebx
0x18002791d  cmovnz  eax, edx
0x180027920  mov     edx, eax
0x180027922  jmp     loc_180027767
```
