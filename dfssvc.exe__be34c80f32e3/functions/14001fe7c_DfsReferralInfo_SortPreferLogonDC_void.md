# DfsReferralInfo::SortPreferLogonDC(void)

- ea: `0x14001fe7c`
- end: `0x140020140`
- name: `?SortPreferLogonDC@DfsReferralInfo@@AEAAXXZ`
- size: `708`
- prototype: `void __fastcall(DfsReferralInfo *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001f3a0`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x140006bf0`
- `0x14001e548`
- `0x14001fe7c`
- `0x14004a454`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14001ff0f`
- `ntdll!RtlCompareUnicodeString` at `0x14001ff29`
- `ntdll!RtlCompareUnicodeString` at `0x140020061`
- `ntdll!RtlCompareUnicodeString` at `0x14001ff0f`
- `ntdll!RtlCompareUnicodeString` at `0x14001ff29`
- `ntdll!RtlCompareUnicodeString` at `0x140020061`
- `ntdll!RtlInitUnicodeString` at `0x14001fed6`
- `ntdll!RtlInitUnicodeString` at `0x14001feed`
- `ntdll!RtlInitUnicodeString` at `0x14001fed6`
- `ntdll!RtlInitUnicodeString` at `0x14001feed`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001ff4a`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001ffbc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001ff4a`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001ffbc`

## pseudocode

```c
void __fastcall DfsReferralInfo::SortPreferLogonDC(DfsReferralInfo *this)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  const UNICODE_STRING *v4; // rbx
  __int64 LocalMachineName; // rax
  const unsigned __int16 *v6; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  PCWSTR v10; // r11
  unsigned int v11; // edx
  unsigned int v12; // ebx
  __m128i *v13; // rax
  UNICODE_STRING v14; // xmm0
  unsigned int v15; // ecx
  unsigned __int16 v16; // ax
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // r9d
  __int64 i; // r10
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // r9
  UNICODE_STRING v24; // [rsp+20h] [rbp-40h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-10h] BYREF

  if ( !*((_BYTE *)CConfigurationSettings::_GetInstance((unsigned int *)this) + 8) )
    return;
  if ( *(_DWORD *)this <= 1u )
    return;
  v2 = *((_QWORD *)this + 3);
  DestinationString = 0;
  String2 = 0;
  v3 = *(_QWORD *)(v2 + 8);
  RtlInitUnicodeString(&DestinationString, L"NETLOGON");
  RtlInitUnicodeString(&String2, L"SYSVOL");
  v4 = (const UNICODE_STRING *)(v3 + 24);
  if ( v4 )
  {
    if ( v4->Length && RtlCompareUnicodeString(v4, &DestinationString, 1u) && RtlCompareUnicodeString(v4, &String2, 1u) )
      return;
  }
  v24 = 0;
  RtlInitUnicodeStringEx(&v24, 0);
  LocalMachineName = DfsGetLocalMachineName(3);
  v6 = (const unsigned __int16 *)LocalMachineName;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(LocalMachineName + 2 * v7) );
  v8 = v7 + 1;
  if ( 2 * v8 > 0xFFFF )
  {
    v23 = 206;
  }
  else
  {
    v9 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
    if ( v9 )
    {
      StringCchCopyW(v9, v8, v6);
      RtlInitUnicodeStringEx(&v24, v10);
      v11 = 0;
      for ( String1 = 0; v11 < v24.Length >> 1; ++v11 )
      {
        if ( v24.Buffer[v11] == 46 )
          break;
        if ( !v24.Buffer[v11] )
          break;
      }
      v12 = 0;
      for ( v24.Length = 2 * v11; v12 < *(_DWORD *)this; ++v12 )
      {
        v13 = (__m128i *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL * v12 + 8) + 16LL) + 24LL);
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL * v12 + 8) + 16LL) != -24 )
        {
          v14 = (UNICODE_STRING)*v13;
          v15 = 0;
          v16 = _mm_cvtsi128_si32(*v13);
          String1 = v14;
          if ( v16 >> 1 )
          {
            do
            {
              if ( String1.Buffer[v15] == 46 )
                break;
              if ( !String1.Buffer[v15] )
                break;
              ++v15;
            }
            while ( v15 < v16 >> 1 );
          }
          String1.Length = 2 * v15;
          if ( !RtlCompareUnicodeString(&String1, &v24, 1u) )
            break;
        }
      }
      if ( v12 < *(_DWORD *)this )
      {
        v17 = *((_QWORD *)this + 3);
        v18 = 24LL * v12;
        v19 = *(_DWORD *)(v18 + v17);
        for ( i = *(_QWORD *)(v18 + v17 + 8); v12; *(_QWORD *)(v18 + v21 + 32) = *(_QWORD *)(v21 + 24LL * v12 + 8) )
        {
          v21 = *((_QWORD *)this + 3);
          *(_DWORD *)(v18 + v21) = *(_DWORD *)(v21 + 24LL * --v12);
          v18 -= 24;
        }
        v22 = *((_QWORD *)this + 3);
        *(_DWORD *)v22 = v19;
        *(_QWORD *)(v22 + 8) = i;
      }
      operator delete(v24.Buffer);
      return;
    }
    v23 = 8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x880) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 12, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids, v23);
  }
}

```

## disassembly

```asm
0x14001fe7c  mov     rax, rsp
0x14001fe7f  mov     [rax+8], rbx
0x14001fe83  mov     [rax+10h], rsi
0x14001fe87  mov     [rax+18h], rdi
0x14001fe8b  mov     [rax+20h], r14
0x14001fe8f  push    rbp
0x14001fe90  mov     rbp, rsp
0x14001fe93  sub     rsp, 60h
0x14001fe97  mov     rdi, rcx
0x14001fe9a  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14001fe9f  xor     r14d, r14d
0x14001fea2  cmp     [rax+8], r14b
0x14001fea6  jz      loc_140020125
0x14001feac  cmp     dword ptr [rdi], 1
0x14001feaf  jbe     loc_140020125
0x14001feb5  mov     rax, [rdi+18h]
0x14001feb9  lea     rdx, SourceString; "NETLOGON"
0x14001fec0  xorps   xmm0, xmm0
0x14001fec3  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001fec7  xorps   xmm1, xmm1
0x14001feca  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001fece  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14001fed2  mov     rbx, [rax+8]
0x14001fed6  call    cs:__imp_RtlInitUnicodeString
0x14001fedd  nop     dword ptr [rax+rax+00h]
0x14001fee2  lea     rdx, aSysvol; "SYSVOL"
0x14001fee9  lea     rcx, [rbp+String2]; DestinationString
0x14001feed  call    cs:__imp_RtlInitUnicodeString
0x14001fef4  nop     dword ptr [rax+rax+00h]
0x14001fef9  add     rbx, 18h
0x14001fefd  jz      short loc_14001FF3D
0x14001feff  cmp     [rbx], r14w
0x14001ff03  jz      short loc_14001FF3D
0x14001ff05  mov     r8b, 1; CaseInsensitive
0x14001ff08  lea     rdx, [rbp+DestinationString]; String2
0x14001ff0c  mov     rcx, rbx; String1
0x14001ff0f  call    cs:__imp_RtlCompareUnicodeString
0x14001ff16  nop     dword ptr [rax+rax+00h]
0x14001ff1b  test    eax, eax
0x14001ff1d  jz      short loc_14001FF3D
0x14001ff1f  mov     r8b, 1; CaseInsensitive
0x14001ff22  lea     rdx, [rbp+String2]; String2
0x14001ff26  mov     rcx, rbx; String1
0x14001ff29  call    cs:__imp_RtlCompareUnicodeString
0x14001ff30  nop     dword ptr [rax+rax+00h]
0x14001ff35  test    eax, eax
0x14001ff37  jnz     loc_140020125
0x14001ff3d  xorps   xmm0, xmm0
0x14001ff40  lea     rcx, [rbp+var_40]; DestinationString
0x14001ff44  xor     edx, edx; SourceString
0x14001ff46  movups  xmmword ptr [rbp+var_40.Length], xmm0
0x14001ff4a  call    cs:__imp_RtlInitUnicodeStringEx
0x14001ff51  nop     dword ptr [rax+rax+00h]
0x14001ff56  mov     ecx, 3
0x14001ff5b  call    ?DfsGetLocalMachineName@@YAPEBGW4DFS_HOST_NAME_TYPE@CLocalMachine@@@Z; DfsGetLocalMachineName(CLocalMachine::DFS_HOST_NAME_TYPE)
0x14001ff60  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001ff64  mov     rsi, rax
0x14001ff67  mov     rbx, rcx
0x14001ff6a  inc     rbx
0x14001ff6d  cmp     [rax+rbx*2], r14w
0x14001ff72  jnz     short loc_14001FF6A
0x14001ff74  inc     rbx
0x14001ff77  lea     rax, [rbx+rbx]
0x14001ff7b  cmp     rax, 0FFFFh
0x14001ff81  ja      loc_1400200DA
0x14001ff87  mov     eax, 2
0x14001ff8c  mul     rbx
0x14001ff8f  cmovo   rax, rcx
0x14001ff93  mov     rcx, rax; Size
0x14001ff96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ff9b  mov     r11, rax
0x14001ff9e  test    rax, rax
0x14001ffa1  jz      loc_1400200D2
0x14001ffa7  mov     r8, rsi; unsigned __int16 *
0x14001ffaa  mov     rdx, rbx; unsigned __int64
0x14001ffad  mov     rcx, rax; unsigned __int16 *
0x14001ffb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001ffb5  mov     rdx, r11; SourceString
0x14001ffb8  lea     rcx, [rbp+var_40]; DestinationString
0x14001ffbc  call    cs:__imp_RtlInitUnicodeStringEx
0x14001ffc3  nop     dword ptr [rax+rax+00h]
0x14001ffc8  movzx   r8d, [rbp+var_40.Length]
0x14001ffcd  xorps   xmm0, xmm0
0x14001ffd0  shr     r8d, 1
0x14001ffd3  mov     edx, r14d
0x14001ffd6  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14001ffda  jz      short loc_14001FFF7
0x14001ffdc  mov     rax, [rbp+var_40.Buffer]
0x14001ffe0  mov     ecx, edx
0x14001ffe2  cmp     word ptr [rax+rcx*2], 2Eh ; '.'
0x14001ffe7  jz      short loc_14001FFF7
0x14001ffe9  cmp     [rax+rcx*2], r14w
0x14001ffee  jz      short loc_14001FFF7
0x14001fff0  inc     edx
0x14001fff2  cmp     edx, r8d
0x14001fff5  jb      short loc_14001FFDC
0x14001fff7  add     dx, dx
0x14001fffa  mov     ebx, r14d
0x14001fffd  mov     [rbp+var_40.Length], dx
0x140020001  cmp     [rdi], r14d
0x140020004  jbe     short loc_140020077
0x140020006  mov     eax, ebx
0x140020008  lea     rcx, [rax+rax*2]
0x14002000c  mov     rax, [rdi+18h]
0x140020010  mov     rcx, [rax+rcx*8+8]
0x140020015  mov     rax, [rcx+10h]
0x140020019  add     rax, 18h
0x14002001d  jz      short loc_140020071
0x14002001f  movups  xmm0, xmmword ptr [rax]
0x140020022  mov     ecx, r14d
0x140020025  movd    eax, xmm0
0x140020029  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14002002d  movzx   edx, ax
0x140020030  shr     edx, 1
0x140020032  jz      short loc_14002004F
0x140020034  mov     r8, [rbp+String1.Buffer]
0x140020038  mov     eax, ecx
0x14002003a  cmp     word ptr [r8+rax*2], 2Eh ; '.'
0x140020040  jz      short loc_14002004F
0x140020042  cmp     [r8+rax*2], r14w
0x140020047  jz      short loc_14002004F
0x140020049  inc     ecx
0x14002004b  cmp     ecx, edx
0x14002004d  jb      short loc_140020038
0x14002004f  add     cx, cx
0x140020052  lea     rdx, [rbp+var_40]; String2
0x140020056  mov     [rbp+String1.Length], cx
0x14002005a  mov     r8b, 1; CaseInsensitive
0x14002005d  lea     rcx, [rbp+String1]; String1
0x140020061  call    cs:__imp_RtlCompareUnicodeString
0x140020068  nop     dword ptr [rax+rax+00h]
0x14002006d  test    eax, eax
0x14002006f  jz      short loc_140020077
0x140020071  inc     ebx
0x140020073  cmp     ebx, [rdi]
0x140020075  jb      short loc_140020006
0x140020077  cmp     ebx, [rdi]
0x140020079  jnb     short loc_1400200C7
0x14002007b  mov     eax, ebx
0x14002007d  lea     rcx, [rax+rax*2]
0x140020081  mov     rax, [rdi+18h]
0x140020085  lea     r8, ds:0[rcx*8]
0x14002008d  mov     r9d, [r8+rax]
0x140020091  mov     r10, [r8+rax+8]
0x140020096  test    ebx, ebx
0x140020098  jz      short loc_1400200BC
0x14002009a  mov     rdx, [rdi+18h]
0x14002009e  sub     ebx, 1
0x1400200a1  lea     rcx, [rbx+rbx*2]
0x1400200a5  mov     eax, [rdx+rcx*8]
0x1400200a8  mov     [r8+rdx], eax
0x1400200ac  lea     r8, [r8-18h]
0x1400200b0  mov     rax, [rdx+rcx*8+8]
0x1400200b5  mov     [r8+rdx+20h], rax
0x1400200ba  jnz     short loc_14002009A
0x1400200bc  mov     rax, [rdi+18h]
0x1400200c0  mov     [rax], r9d
0x1400200c3  mov     [rax+8], r10
0x1400200c7  mov     rcx, [rbp+var_40.Buffer]; Block
0x1400200cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400200d0  jmp     short loc_140020125
0x1400200d2  mov     r9d, 8
0x1400200d8  jmp     short loc_1400200E0
0x1400200da  mov     r9d, 0CEh
0x1400200e0  lea     rax, WPP_GLOBAL_Control
0x1400200e7  cmp     cs:WPP_GLOBAL_Control, rax
0x1400200ee  jz      short loc_140020125
0x1400200f0  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400200f7  test    rcx, rcx
0x1400200fa  jz      short loc_140020125
0x1400200fc  mov     eax, 80h
0x140020101  bts     eax, 0Bh
0x140020105  test    [rcx+1Ch], eax
0x140020108  jz      short loc_140020125
0x14002010a  cmp     byte ptr [rcx+19h], 1
0x14002010e  jb      short loc_140020125
0x140020110  mov     rcx, [rcx+10h]
0x140020114  lea     r8, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids
0x14002011b  mov     edx, 0Ch
0x140020120  call    WPP_SF_D
0x140020125  lea     r11, [rsp+60h+var_s0]
0x14002012a  mov     rbx, [r11+10h]
0x14002012e  mov     rsi, [r11+18h]
0x140020132  mov     rdi, [r11+20h]
0x140020136  mov     r14, [r11+28h]
0x14002013a  mov     rsp, r11
0x14002013d  pop     rbp
0x14002013e  retn
```
