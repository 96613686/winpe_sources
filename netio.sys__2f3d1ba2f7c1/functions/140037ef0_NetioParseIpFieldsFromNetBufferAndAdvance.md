# NetioParseIpFieldsFromNetBufferAndAdvance

- ea: `0x140037ef0`
- end: `0x140038154`
- name: `NetioParseIpFieldsFromNetBufferAndAdvance`
- size: `612`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER NetBuffer@<rcx>, __int64 Storage, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140037e40`
- `0x1400532a0`

## callees

- `0x140037ef0`
- `0x14003819c`
- `0x140038400`
- `0x1400384f0`
- `0x140042740`
- `0x140051bd0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038082`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400380ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038082`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400380ee`
- `NDIS!NdisGetDataBuffer` at `0x14007cf51`
- `NDIS!NdisGetDataBuffer` at `0x14007cf51`

## pseudocode

```c
__int64 __fastcall NetioParseIpFieldsFromNetBufferAndAdvance(
        PNET_BUFFER NetBuffer,
        unsigned __int16 a2,
        __int64 a3,
        bool *a4,
        ULONG *Storage,
        _QWORD *a6)
{
  ULONG *v6; // r13
  PMDL *p_CurrentMdl; // r15
  _QWORD *v8; // r12
  unsigned __int16 AddressFamily; // si
  int v13; // edi
  ULONG v14; // eax
  struct _MDL *v15; // rcx
  char *v16; // rdx
  __int64 CurrentMdlOffset; // rcx
  ULONG v18; // eax
  ULONG v19; // edx
  bool v20; // al
  ULONG v21; // r11d
  __int64 v22; // rbx
  int *v24; // rsi
  ULONG v25; // r10d
  _DWORD *v26; // r15
  unsigned __int8 *v27; // r9
  ULONG v28; // r8d
  unsigned __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // r10d
  struct _MDL *v32; // rcx
  char *MappedSystemVa; // rdx
  __int64 v34; // rax
  _WORD *DataBuffer; // rax

  v6 = Storage;
  p_CurrentMdl = &NetBuffer->CurrentMdl;
  v8 = a6;
  AddressFamily = a2;
  *Storage = 0;
  v13 = -1073741285;
  *a4 = 1;
  *v8 = 0;
  if ( a2
    || ((v32 = *p_CurrentMdl, ((*p_CurrentMdl)->MdlFlags & 5) == 0)
      ? (MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v32, 0, MmCached, 0, 0, 0x40000000u))
      : (MappedSystemVa = (char *)v32->MappedSystemVa),
        &MappedSystemVa[NetBuffer->CurrentMdlOffset] && (AddressFamily = NetioPhGetAddressFamily()) != 0) )
  {
    if ( AddressFamily == 2 )
    {
      v14 = 20;
    }
    else
    {
      if ( AddressFamily != 23 )
        return (unsigned int)v13;
      v14 = 40;
    }
    if ( NetBuffer->DataLength >= v14 )
    {
      v15 = *p_CurrentMdl;
      v16 = (char *)(((*p_CurrentMdl)->MdlFlags & 5) != 0
                   ? v15->MappedSystemVa
                   : MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000000u));
      CurrentMdlOffset = NetBuffer->CurrentMdlOffset;
      *(_QWORD *)a3 = &v16[CurrentMdlOffset];
      if ( &v16[CurrentMdlOffset] )
      {
        NetioParseIpFieldsFromIpHeader(AddressFamily, a3);
        v18 = *(_DWORD *)(a3 + 44);
        if ( v18 <= NetBuffer->DataLength && *(_DWORD *)(a3 + 8) <= v18 )
        {
          v19 = (*p_CurrentMdl)->ByteCount - NetBuffer->CurrentMdlOffset;
          *v6 = v19;
          v20 = *(_DWORD *)(a3 + 44) <= v19;
          *a4 = v20;
          v21 = *(_DWORD *)(a3 + 8);
          if ( v20 )
          {
            v22 = *(_QWORD *)a3 + v21;
            if ( AddressFamily != 23 )
            {
LABEL_12:
              *v8 = v22;
              return 0;
            }
            v24 = (int *)(a3 + 16);
            v25 = *v6 - v21;
            v26 = (_DWORD *)(a3 + 40);
            v27 = (unsigned __int8 *)(*(_QWORD *)a3 + v21);
            v28 = 0;
            while ( 1 )
            {
              v29 = (unsigned int)*v26;
              if ( (unsigned int)v29 > 0x3C || (v30 = 0x1000080000000001LL, !_bittest64(&v30, v29)) )
              {
                v13 = 0;
                goto LABEL_23;
              }
              if ( (unsigned __int64)v28 + 8 > v25 )
                break;
              v34 = (_DWORD)v29 == 44 ? 8LL : 8 * (unsigned int)v27[1] + 8;
              LODWORD(v29) = *v27;
              v28 += v34;
              *v26 = v29;
              if ( v28 > v25 )
                break;
              v27 += v34;
            }
            v28 = 0;
LABEL_23:
            *v24 += v28;
            v31 = *v24;
            if ( v13 >= 0 )
            {
              if ( (_DWORD)v29 != 44
                || (*(_BYTE *)(a3 + 13) = 2 - ((*(_WORD *)(v22 + 2) & 0x100) != 0),
                    v13 = NetioPhSkipAllIpv6OptionsContiguous(v22, 0, *v6 - v31 - v21, (int)a3 + 40, a3 + 16),
                    v13 >= 0) )
              {
                v22 += (unsigned int)*v24;
                goto LABEL_12;
              }
            }
          }
          else
          {
            NetioAdvanceNetBuffer(NetBuffer, v21);
            if ( AddressFamily != 23 )
              return 0;
            v13 = NetioPhSkipAllIpv6Options(NetBuffer);
            if ( v13 >= 0 )
            {
              if ( *(_DWORD *)(a3 + 40) != 44 )
                return 0;
              Storage = 0;
              DataBuffer = NdisGetDataBuffer(NetBuffer, 8u, &Storage, 1u, 0);
              if ( DataBuffer )
              {
                *(_BYTE *)(a3 + 13) = 2 - ((DataBuffer[1] & 0x100) != 0);
                v13 = NetioPhSkipAllIpv6Options(NetBuffer);
                if ( v13 >= 0 )
                  return 0;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140037ef0  push    rbx
0x140037ef2  push    rbp
0x140037ef3  push    rsi
0x140037ef4  push    rdi
0x140037ef5  push    r12
0x140037ef7  push    r13
0x140037ef9  push    r14
0x140037efb  push    r15
0x140037efd  sub     rsp, 38h
0x140037f01  mov     r13, [rsp+78h+Storage]
0x140037f09  lea     r15, [rcx+8]
0x140037f0d  mov     r12, [rsp+78h+arg_28]
0x140037f15  movzx   esi, dx
0x140037f18  xor     edx, edx; AccessMode
0x140037f1a  mov     rbp, r9
0x140037f1d  mov     r14, r8
0x140037f20  mov     rbx, rcx
0x140037f23  mov     [r13+0], edx
0x140037f27  mov     edi, 0C000021Bh
0x140037f2c  mov     byte ptr [r9], 1
0x140037f30  mov     [r12], rdx
0x140037f34  test    si, si
0x140037f37  jz      loc_1400380AA
0x140037f3d  cmp     si, 2
0x140037f41  jnz     loc_140038059
0x140037f47  mov     eax, 14h
0x140037f4c  cmp     [rbx+18h], eax
0x140037f4f  jb      short loc_140037FBA
0x140037f51  mov     rcx, [r15]; MemoryDescriptorList
0x140037f54  test    byte ptr [rcx+0Ah], 5
0x140037f58  jz      loc_14003806D
0x140037f5e  mov     rdx, [rcx+18h]
0x140037f62  mov     ecx, [rbx+10h]
0x140037f65  add     rcx, rdx
0x140037f68  mov     [r14], rcx
0x140037f6b  jz      short loc_140037FBA
0x140037f6d  mov     rdx, r14
0x140037f70  movzx   ecx, si
0x140037f73  call    NetioParseIpFieldsFromIpHeader
0x140037f78  mov     eax, [r14+2Ch]
0x140037f7c  cmp     eax, [rbx+18h]
0x140037f7f  ja      short loc_140037FBA
0x140037f81  cmp     [r14+8], eax
0x140037f85  ja      short loc_140037FBA
0x140037f87  mov     rax, [r15]
0x140037f8a  mov     edx, [rax+28h]
0x140037f8d  sub     edx, [rbx+10h]
0x140037f90  mov     [r13+0], edx
0x140037f94  cmp     [r14+2Ch], edx
0x140037f98  setbe   al
0x140037f9b  mov     [rbp+0], al
0x140037f9e  mov     r11d, [r14+8]
0x140037fa2  ja      short loc_140037FCE
0x140037fa4  mov     ebx, r11d
0x140037fa7  add     rbx, [r14]
0x140037faa  cmp     si, 17h
0x140037fae  jz      short loc_140038007
0x140037fb0  mov     [r12], rbx
0x140037fb4  xor     r15d, r15d
0x140037fb7  mov     edi, r15d
0x140037fba  mov     eax, edi
0x140037fbc  add     rsp, 38h
0x140037fc0  pop     r15
0x140037fc2  pop     r14
0x140037fc4  pop     r13
0x140037fc6  pop     r12
0x140037fc8  pop     rdi
0x140037fc9  pop     rsi
0x140037fca  pop     rbp
0x140037fcb  pop     rbx
0x140037fcc  retn
0x140037fce  mov     edx, r11d
0x140037fd1  mov     rcx, rbx
0x140037fd4  call    NetioAdvanceNetBuffer
0x140037fd9  cmp     si, 17h
0x140037fdd  jnz     short loc_140037FB4
0x140037fdf  lea     rsi, [r14+28h]
0x140037fe3  mov     dl, 1
0x140037fe5  mov     r8, rsi
0x140037fe8  lea     r9, [r14+10h]
0x140037fec  mov     rcx, rbx; NetBuffer
0x140037fef  call    NetioPhSkipAllIpv6Options
0x140037ff4  xor     r15d, r15d
0x140037ff7  mov     edi, eax
0x140037ff9  test    eax, eax
0x140037ffb  js      short loc_140037FBA
0x140037ffd  cmp     dword ptr [rsi], 2Ch ; ','
0x140038000  jnz     short loc_140037FB7
0x140038002  jmp     loc_14007CF2F
0x140038007  mov     r10d, [r13+0]
0x14003800b  lea     rsi, [r14+10h]
0x14003800f  sub     r10d, r11d
0x140038012  lea     r15, [r14+28h]
0x140038016  xor     ebp, ebp
0x140038018  mov     r9, rbx
0x14003801b  mov     r8d, ebp
0x14003801e  mov     edx, [r15]
0x140038021  cmp     edx, 3Ch ; '<'
0x140038024  ja      short loc_140038036
0x140038026  mov     rcx, 1000080000000001h
0x140038030  bt      rcx, rdx
0x140038034  jb      short loc_140038096
0x140038036  mov     edi, ebp
0x140038038  add     [rsi], r8d
0x14003803b  mov     r10d, [rsi]
0x14003803e  test    edi, edi
0x140038040  js      loc_140037FBA
0x140038046  cmp     edx, 2Ch ; ','
0x140038049  jz      loc_140038112
0x14003804f  mov     eax, [rsi]
0x140038051  add     rbx, rax
0x140038054  jmp     loc_140037FB0
0x140038059  cmp     si, 17h
0x14003805d  jnz     loc_140037FBA
0x140038063  mov     eax, 28h ; '('
0x140038068  jmp     loc_140037F4C
0x14003806d  xor     r9d, r9d; RequestedAddress
0x140038070  mov     [rsp+78h+Priority], 40000000h; Priority
0x140038078  mov     [rsp+78h+BugCheckOnFailure], edx; BugCheckOnFailure
0x14003807c  xor     edx, edx; AccessMode
0x14003807e  lea     r8d, [r9+1]; CacheType
0x140038082  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140038089  nop     dword ptr [rax+rax+00h]
0x14003808e  mov     rdx, rax
0x140038091  jmp     loc_140037F62
0x140038096  mov     ecx, r8d
0x140038099  add     rcx, 8
0x14003809d  mov     eax, r10d
0x1400380a0  cmp     rcx, rax
0x1400380a3  jbe     short loc_1400380FF
0x1400380a5  mov     r8d, ebp
0x1400380a8  jmp     short loc_140038038
0x1400380aa  mov     rcx, [r15]; MemoryDescriptorList
0x1400380ad  test    byte ptr [rcx+0Ah], 5
0x1400380b1  jz      short loc_1400380DB
0x1400380b3  mov     rdx, [rcx+18h]
0x1400380b7  mov     ecx, [rbx+10h]
0x1400380ba  add     rcx, rdx
0x1400380bd  jz      loc_140037FBA
0x1400380c3  call    NetioPhGetAddressFamily
0x1400380c8  xor     edx, edx
0x1400380ca  movzx   esi, ax
0x1400380cd  test    ax, ax
0x1400380d0  jz      loc_140037FBA
0x1400380d6  jmp     loc_140037F3D
0x1400380db  xor     r9d, r9d; RequestedAddress
0x1400380de  mov     [rsp+78h+Priority], 40000000h; Priority
0x1400380e6  mov     [rsp+78h+BugCheckOnFailure], edx; BugCheckOnFailure
0x1400380ea  lea     r8d, [r9+1]; CacheType
0x1400380ee  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400380f5  nop     dword ptr [rax+rax+00h]
0x1400380fa  mov     rdx, rax
0x1400380fd  jmp     short loc_1400380B7
0x1400380ff  cmp     edx, 2Ch ; ','
0x140038102  jnz     loc_14007CF08
0x140038108  mov     eax, 8
0x14003810d  jmp     loc_14007CF14
0x140038112  movzx   eax, word ptr [rbx+2]
0x140038116  mov     ecx, 100h
0x14003811b  and     ax, cx
0x14003811e  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi
0x140038123  neg     ax
0x140038126  mov     r9, r15
0x140038129  mov     rcx, rbx
0x14003812c  sbb     al, al
0x14003812e  xor     edx, edx
0x140038130  add     al, 2
0x140038132  mov     [r14+0Dh], al
0x140038136  mov     r8d, [r13+0]
0x14003813a  sub     r8d, r10d
0x14003813d  sub     r8d, r11d
0x140038140  call    NetioPhSkipAllIpv6OptionsContiguous
0x140038145  mov     edi, eax
0x140038147  test    eax, eax
0x140038149  js      loc_140037FBA
0x14003814f  jmp     loc_14003804F
0x14007cf08  movzx   eax, byte ptr [r9+1]
0x14007cf0d  lea     eax, ds:8[rax*8]
0x14007cf14  movzx   edx, byte ptr [r9]
0x14007cf18  add     r8d, eax
0x14007cf1b  mov     [r15], edx
0x14007cf1e  cmp     r8d, r10d
0x14007cf21  ja      loc_1400380A5
0x14007cf27  add     r9, rax
0x14007cf2a  jmp     loc_14003801E
0x14007cf2f  mov     r9d, 1; AlignMultiple
0x14007cf35  mov     [rsp+78h+Storage], r15
0x14007cf3d  lea     r8, [rsp+78h+Storage]; Storage
0x14007cf45  mov     [rsp+78h+BugCheckOnFailure], r15d; AlignOffset
0x14007cf4a  mov     rcx, rbx; NetBuffer
0x14007cf4d  lea     edx, [r9+7]; BytesNeeded
0x14007cf51  call    cs:__imp_NdisGetDataBuffer
0x14007cf58  nop     dword ptr [rax+rax+00h]
0x14007cf5d  test    rax, rax
0x14007cf60  jz      loc_140037FBA
0x14007cf66  movzx   eax, word ptr [rax+2]
0x14007cf6a  lea     r9, [r14+10h]
0x14007cf6e  mov     ecx, 100h
0x14007cf73  mov     r8, rsi
0x14007cf76  and     ax, cx
0x14007cf79  mov     rcx, rbx; NetBuffer
0x14007cf7c  neg     ax
0x14007cf7f  sbb     al, al
0x14007cf81  xor     edx, edx
0x14007cf83  add     al, 2
0x14007cf85  mov     [r14+0Dh], al
0x14007cf89  call    NetioPhSkipAllIpv6Options
0x14007cf8e  mov     edi, eax
0x14007cf90  test    eax, eax
0x14007cf92  js      loc_140037FBA
0x14007cf98  jmp     loc_140037FB7
```
