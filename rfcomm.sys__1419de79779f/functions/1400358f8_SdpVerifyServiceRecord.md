# SdpVerifyServiceRecord

- ea: `0x1400358f8`
- end: `0x140035ab1`
- name: `SdpVerifyServiceRecord`
- size: `441`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003468c`

## callees

- `0x14001fc70`
- `0x14003573c`
- `0x1400358f8`
- `0x140036620`

## pseudocode

```c
__int64 __fastcall SdpVerifyServiceRecord(unsigned __int8 *a1, unsigned int a2, char *a3, _WORD *a4)
{
  unsigned int v4; // r14d
  USHORT v8; // ax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD); // rax
  int v10; // edx
  char *v11; // r9
  __int64 v12; // r9
  SdpAttributeRange v14; // [rsp+40h] [rbp-38h] BYREF
  __int128 v15; // [rsp+50h] [rbp-28h] BYREF
  __int128 v16; // [rsp+60h] [rbp-18h]
  int v17; // [rsp+D0h] [rbp+58h] BYREF

  v17 = (int)a3;
  v4 = 0;
  while ( 1 )
  {
    v15 = 0u;
    v8 = word_140022230[12 * v4];
    v16 = 0;
    v14.maxAttribute = v8;
    v14.minAttribute = v8;
    BYTE12(v16) = 1;
    DWORD2(v15) = 0;
    if ( (int)SdpFA_Search((struct _SDP_FIND_ATTRIBUTES *)&v15, &v14, (unsigned int)a3, a1, a2) < 0 || !(_QWORD)v15 )
    {
      v10 = 0;
      goto LABEL_22;
    }
    v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))qword_140022240[3 * v4];
    if ( v9 )
    {
      v10 = v9(v15, DWORD2(v15), 0);
      goto LABEL_19;
    }
    if ( (byte_140022232[24 * v4] & 0x10) == 0 )
      break;
    v11 = (char *)(&off_140022238)[3 * v4];
    LOBYTE(a3) = byte_140022234[24 * v4];
    v17 = 0;
    v10 = SdpVerifySequenceOf(v15, DWORD2(v15), (_DWORD)a3, (_DWORD)v11, (__int64)&v17, 0, 0);
    if ( v10 < 0 )
      goto LABEL_25;
    if ( !v17 )
      v10 = -1073741811;
LABEL_19:
    if ( v10 < 0 )
      goto LABEL_25;
LABEL_22:
    if ( ++v4 >= 0xE )
      return (unsigned int)v10;
  }
  if ( *(_BYTE *)v15 >> 3 == byte_140022234[24 * v4] )
  {
    a3 = (char *)(&off_140022238)[3 * v4];
    if ( a3 )
    {
      if ( *a3 )
      {
        LODWORD(v12) = 0;
        v10 = 0;
        while ( g_IndexToDataSize[*(_BYTE *)v15 & 7] != (unsigned __int8)a3[(unsigned int)v12] )
        {
          v12 = (unsigned int)(v12 + 1);
          if ( !a3[v12] )
            goto LABEL_17;
        }
      }
      else
      {
LABEL_17:
        v10 = -1073741811;
      }
    }
    else
    {
      v10 = 0;
    }
    goto LABEL_19;
  }
  v10 = -1073741811;
LABEL_25:
  *a4 = word_140022230[12 * v4];
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400358f8  mov     [rsp-40h+arg_10], r8d
0x1400358fd  push    rbp
0x1400358fe  push    rbx
0x1400358ff  push    rsi
0x140035900  push    rdi
0x140035901  push    r12
0x140035903  push    r13
0x140035905  push    r14
0x140035907  push    r15
0x140035909  mov     rbp, rsp
0x14003590c  sub     rsp, 78h
0x140035910  xor     r11d, r11d
0x140035913  lea     rsi, cs:140000000h
0x14003591a  mov     r14d, r11d
0x14003591d  mov     r15, r9
0x140035920  mov     r12d, edx
0x140035923  mov     r13, rcx
0x140035926  mov     eax, r14d
0x140035929  lea     rdx, [rbp+var_38]; struct SdpAttributeRange *
0x14003592d  xorps   xmm0, xmm0
0x140035930  mov     [rsp+78h+var_58], r12d; unsigned int
0x140035935  movups  [rbp+var_28], xmm0
0x140035939  mov     r9, r13; unsigned __int8 *
0x14003593c  lea     rcx, [rbp+var_28]; struct _SDP_FIND_ATTRIBUTES *
0x140035940  lea     rdi, [rax+rax*2]
0x140035944  mov     qword ptr [rbp+var_28], r11
0x140035948  movzx   eax, ds:rva word_140022230[rsi+rdi*8]
0x140035950  movups  [rbp+var_18], xmm0
0x140035954  mov     [rbp+var_38.maxAttribute], ax
0x140035958  mov     [rbp+var_38.minAttribute], ax
0x14003595c  mov     byte ptr [rbp+var_18+0Ch], 1
0x140035960  mov     dword ptr [rbp+var_28+8], r11d
0x140035964  call    ?SdpFA_Search@@YAJPEAU_SDP_FIND_ATTRIBUTES@@PEAUSdpAttributeRange@@KPEAEK@Z; SdpFA_Search(_SDP_FIND_ATTRIBUTES *,SdpAttributeRange *,ulong,uchar *,ulong)
0x140035969  xor     r11d, r11d
0x14003596c  test    eax, eax
0x14003596e  js      loc_140035A6A
0x140035974  mov     rbx, qword ptr [rbp+var_28]
0x140035978  test    rbx, rbx
0x14003597b  jz      loc_140035A6A
0x140035981  mov     esi, dword ptr [rbp+var_28+8]
0x140035984  lea     r10, cs:140000000h
0x14003598b  mov     rax, ds:rva qword_140022240[r10+rdi*8]
0x140035993  test    rax, rax
0x140035996  jz      short loc_1400359AF
0x140035998  xor     r8d, r8d
0x14003599b  mov     edx, esi
0x14003599d  mov     rcx, rbx
0x1400359a0  call    _guard_dispatch_icall
0x1400359a5  mov     edx, eax
0x1400359a7  xor     r11d, r11d
0x1400359aa  jmp     loc_140035A5D
0x1400359af  test    ds:rva byte_140022232[r10+rdi*8], 10h
0x1400359b8  jz      short loc_140035A06
0x1400359ba  mov     r9, ds:rva off_140022238[r10+rdi*8]
0x1400359c2  lea     rax, [rbp+arg_10]
0x1400359c6  mov     r8b, ds:rva byte_140022234[r10+rdi*8]
0x1400359ce  mov     edx, esi
0x1400359d0  mov     [rsp+78h+var_48], r11
0x1400359d5  mov     rcx, rbx
0x1400359d8  mov     [rsp+78h+var_50], r11
0x1400359dd  mov     qword ptr [rsp+78h+var_58], rax
0x1400359e2  mov     [rbp+arg_10], r11d
0x1400359e6  call    SdpVerifySequenceOf
0x1400359eb  xor     r11d, r11d
0x1400359ee  mov     edx, eax
0x1400359f0  test    eax, eax
0x1400359f2  js      loc_140035A83
0x1400359f8  cmp     [rbp+arg_10], r11d
0x1400359fc  mov     eax, 0C000000Dh
0x140035a01  cmovz   edx, eax
0x140035a04  jmp     short loc_140035A5D
0x140035a06  movzx   ecx, byte ptr [rbx]
0x140035a09  mov     al, cl
0x140035a0b  shr     al, 3
0x140035a0e  cmp     al, ds:rva byte_140022234[r10+rdi*8]
0x140035a16  jnz     short loc_140035A7C
0x140035a18  mov     r8, ds:rva off_140022238[r10+rdi*8]
0x140035a20  test    r8, r8
0x140035a23  jz      short loc_140035A5A
0x140035a25  cmp     [r8], r11b
0x140035a28  jz      short loc_140035A53
0x140035a2a  mov     eax, ecx
0x140035a2c  mov     r9d, r11d
0x140035a2f  and     eax, 7
0x140035a32  mov     edx, r11d
0x140035a35  mov     r10d, ds:rva g_IndexToDataSize[r10+rax*4]
0x140035a3d  mov     eax, r9d
0x140035a40  movzx   ecx, byte ptr [rax+r8]
0x140035a45  cmp     r10d, ecx
0x140035a48  jz      short loc_140035A5D
0x140035a4a  inc     r9d
0x140035a4d  cmp     [r9+r8], r11b
0x140035a51  jnz     short loc_140035A3D
0x140035a53  mov     edx, 0C000000Dh
0x140035a58  jmp     short loc_140035A5D
0x140035a5a  mov     edx, r11d
0x140035a5d  test    edx, edx
0x140035a5f  js      short loc_140035A83
0x140035a61  lea     rsi, cs:140000000h
0x140035a68  jmp     short loc_140035A6D
0x140035a6a  mov     edx, r11d
0x140035a6d  inc     r14d
0x140035a70  cmp     r14d, 0Eh
0x140035a74  jb      loc_140035926
0x140035a7a  jmp     short loc_140035A9D
0x140035a7c  mov     edx, 0C000000Dh
0x140035a81  jmp     short loc_140035A8A
0x140035a83  lea     r10, cs:140000000h
0x140035a8a  cmp     r14d, 0Eh
0x140035a8e  jnb     short loc_140035A9D
0x140035a90  movzx   eax, ds:rva word_140022230[r10+rdi*8]
0x140035a99  mov     [r15], ax
0x140035a9d  mov     eax, edx
0x140035a9f  add     rsp, 78h
0x140035aa3  pop     r15
0x140035aa5  pop     r14
0x140035aa7  pop     r13
0x140035aa9  pop     r12
0x140035aab  pop     rdi
0x140035aac  pop     rsi
0x140035aad  pop     rbx
0x140035aae  pop     rbp
0x140035aaf  retn
```
