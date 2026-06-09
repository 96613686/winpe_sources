# PsmpUpdateAppUsageInfo

- ea: `0x18000bdc0`
- end: `0x18000c305`
- name: `PsmpUpdateAppUsageInfo`
- size: `1349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003504`

## callees

- `0x18000bdc0`
- `0x18000c3a8`
- `0x18000c5b8`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000bec3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c2fa`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bec3`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000c2fa`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000be2a`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18000be2a`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000be9f`
- `ntdll!RtlCompareUnicodeStrings` at `0x18000be9f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000bf3d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000bf3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c2e3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c2e3`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000be5f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000be5f`

## pseudocode

```c
__int64 __fastcall PsmpUpdateAppUsageInfo(__int64 a1)
{
  __int64 Args; // r8
  __int64 v3; // rax
  int v5; // esi
  wchar_t *v6; // rbx
  WCHAR v7; // di
  int v8; // ecx
  unsigned __int64 v9; // rbx
  __int64 *v10; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *i; // rdi
  signed __int32 *v15; // rsi
  signed __int32 v16; // eax
  __int64 result; // rax
  __int64 v18; // rbx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-2B8h]
  wchar_t Buffer[288]; // [rsp+50h] [rbp-288h] BYREF

  Args = *(_QWORD *)(a1 + 8);
  v3 = -1;
  while ( *(_WORD *)(Args + 2 * v3++ + 2) != 0 )
    ;
  if ( (unsigned __int64)(2 * v3 + 38) <= 0x240 )
    RtlStringCbPrintfExW(Buffer, 2048, (wchar_t *)L"%ws%wc%I64d", Args);
  v5 = 0;
  v6 = Buffer;
  do
  {
    v7 = *v6++;
    v8 = 37 * v5 + RtlUpcaseUnicodeChar(v7);
    v5 = v8;
  }
  while ( v7 );
  v9 = (char *)v6 - (char *)Buffer;
  v10 = &qword_18003FEE8[3 * (v8 & 0x7F)];
  RtlAcquireSRWLockShared(v10 + 2);
  for ( i = (__int64 *)*v10; i != v10; i = (__int64 *)*i )
  {
    v15 = (signed __int32 *)(i - 3);
    if ( v9 == *(i - 1) )
    {
      LOBYTE(v20) = 1;
      if ( !(unsigned int)RtlCompareUnicodeStrings(*((_QWORD *)v15 + 1), v9 >> 1, Buffer, v9 >> 1, v20) )
      {
        _m_prefetchw(v15);
        v16 = *v15;
        while ( v16 > 0 )
        {
          v11 = (unsigned int)v16;
          v16 = _InterlockedCompareExchange(v15, v16 + 1, v16);
          if ( v16 == (_DWORD)v11 )
          {
            result = RtlReleaseSRWLockShared(v10 + 2, v11, v12, v13);
            if ( i != (__int64 *)24 )
            {
              v18 = *(int *)(a1 + 344);
              RtlAcquireSRWLockExclusive(v15 + 30);
              v15[33] = v18;
              v19 = 88 * v18;
              *(_QWORD *)&v15[v19 + 34] = *(_QWORD *)(352 * (v18 + 2) + a1);
              *(_QWORD *)&v15[v19 + 38] = *(_QWORD *)(352 * v18 + a1 + 720) + *(_QWORD *)(352 * v18 + a1 + 3888);
              *(_QWORD *)&v15[v19 + 36] = *(_QWORD *)(352 * v18 + a1 + 712) + *(_QWORD *)(352 * v18 + a1 + 3880);
              *(_QWORD *)&v15[v19 + 40] = *(_QWORD *)(352 * v18 + a1 + 728) + *(_QWORD *)(352 * v18 + a1 + 3896);
              *(_QWORD *)&v15[v19 + 48] = *(_QWORD *)(352 * v18 + a1 + 760) + *(_QWORD *)(352 * v18 + a1 + 3928);
              *(_QWORD *)&v15[v19 + 50] = *(_QWORD *)(352 * v18 + a1 + 768) + *(_QWORD *)(352 * v18 + a1 + 3936);
              *(_QWORD *)&v15[v19 + 52] = *(_QWORD *)(352 * v18 + a1 + 776) + *(_QWORD *)(352 * v18 + a1 + 3944);
              *(_QWORD *)&v15[v19 + 44] = *(_QWORD *)(352 * v18 + a1 + 744) + *(_QWORD *)(352 * v18 + a1 + 3912);
              *(_QWORD *)&v15[v19 + 46] = *(_QWORD *)(352 * v18 + a1 + 752) + *(_QWORD *)(352 * v18 + a1 + 3920);
              *(_QWORD *)&v15[v19 + 70] = *(_QWORD *)(352 * v18 + a1 + 848) + *(_QWORD *)(352 * v18 + a1 + 4016);
              *(_QWORD *)&v15[v19 + 72] = *(_QWORD *)(352 * v18 + a1 + 856) + *(_QWORD *)(352 * v18 + a1 + 4024);
              *(_QWORD *)&v15[v19 + 74] = *(_QWORD *)(352 * v18 + a1 + 864) + *(_QWORD *)(352 * v18 + a1 + 4032);
              *(_QWORD *)&v15[v19 + 76] = *(_QWORD *)(352 * v18 + a1 + 872) + *(_QWORD *)(352 * v18 + a1 + 4040);
              *(_QWORD *)&v15[v19 + 78] = *(_QWORD *)(352 * v18 + a1 + 880) + *(_QWORD *)(352 * v18 + a1 + 4048);
              *(_QWORD *)&v15[v19 + 54] = *(_QWORD *)(352 * v18 + a1 + 784) + *(_QWORD *)(352 * v18 + a1 + 3952);
              *(_QWORD *)&v15[v19 + 106] = *(_QWORD *)(352 * v18 + a1 + 992) + *(_QWORD *)(352 * v18 + a1 + 4160);
              *(_QWORD *)&v15[v19 + 90] = *(_QWORD *)(352 * v18 + a1 + 928) + *(_QWORD *)(352 * v18 + a1 + 4096);
              *(_QWORD *)&v15[v19 + 56] = *(_QWORD *)(352 * v18 + a1 + 792) + *(_QWORD *)(352 * v18 + a1 + 3960);
              *(_QWORD *)&v15[v19 + 108] = *(_QWORD *)(352 * v18 + a1 + 1000) + *(_QWORD *)(352 * v18 + a1 + 4168);
              *(_QWORD *)&v15[v19 + 92] = *(_QWORD *)(352 * v18 + a1 + 936) + *(_QWORD *)(352 * v18 + a1 + 4104);
              *(_QWORD *)&v15[v19 + 58] = *(_QWORD *)(352 * v18 + a1 + 800) + *(_QWORD *)(352 * v18 + a1 + 3968);
              *(_QWORD *)&v15[v19 + 110] = *(_QWORD *)(352 * v18 + a1 + 1008) + *(_QWORD *)(352 * v18 + a1 + 4176);
              *(_QWORD *)&v15[v19 + 94] = *(_QWORD *)(352 * v18 + a1 + 944) + *(_QWORD *)(352 * v18 + a1 + 4112);
              *(_QWORD *)&v15[v19 + 60] = *(_QWORD *)(352 * v18 + a1 + 808) + *(_QWORD *)(352 * v18 + a1 + 3976);
              *(_QWORD *)&v15[v19 + 112] = *(_QWORD *)(352 * v18 + a1 + 1016) + *(_QWORD *)(352 * v18 + a1 + 4184);
              *(_QWORD *)&v15[v19 + 96] = *(_QWORD *)(352 * v18 + a1 + 952) + *(_QWORD *)(352 * v18 + a1 + 4120);
              *(_QWORD *)&v15[v19 + 62] = *(_QWORD *)(352 * v18 + a1 + 816) + *(_QWORD *)(352 * v18 + a1 + 3984);
              *(_QWORD *)&v15[v19 + 114] = *(_QWORD *)(352 * v18 + a1 + 1024) + *(_QWORD *)(352 * v18 + a1 + 4192);
              *(_QWORD *)&v15[v19 + 98] = *(_QWORD *)(352 * v18 + a1 + 960) + *(_QWORD *)(352 * v18 + a1 + 4128);
              *(_QWORD *)&v15[v19 + 64] = *(_QWORD *)(352 * v18 + a1 + 824) + *(_QWORD *)(352 * v18 + a1 + 3992);
              *(_QWORD *)&v15[v19 + 116] = *(_QWORD *)(352 * v18 + a1 + 1032) + *(_QWORD *)(352 * v18 + a1 + 4200);
              *(_QWORD *)&v15[v19 + 100] = *(_QWORD *)(352 * v18 + a1 + 968) + *(_QWORD *)(352 * v18 + a1 + 4136);
              *(_QWORD *)&v15[v19 + 66] = *(_QWORD *)(352 * v18 + a1 + 832) + *(_QWORD *)(352 * v18 + a1 + 4000);
              *(_QWORD *)&v15[v19 + 118] = *(_QWORD *)(352 * v18 + a1 + 1040) + *(_QWORD *)(352 * v18 + a1 + 4208);
              *(_QWORD *)&v15[v19 + 102] = *(_QWORD *)(352 * v18 + a1 + 976) + *(_QWORD *)(352 * v18 + a1 + 4144);
              *(_QWORD *)&v15[v19 + 68] = *(_QWORD *)(352 * v18 + a1 + 840) + *(_QWORD *)(352 * v18 + a1 + 4008);
              *(_QWORD *)&v15[v19 + 120] = *(_QWORD *)(352 * v18 + a1 + 1048) + *(_QWORD *)(352 * v18 + a1 + 4216);
              *(_QWORD *)&v15[v19 + 104] = *(_QWORD *)(352 * v18 + a1 + 984) + *(_QWORD *)(352 * v18 + a1 + 4152);
              RtlReleaseSRWLockExclusive(v15 + 30);
              return PsmpDereferenceAppUsageInfo(i - 3);
            }
            return result;
          }
        }
      }
    }
  }
  return RtlReleaseSRWLockShared(v10 + 2, v11, v12, v13);
}

```

## disassembly

```asm
0x18000bdc0  push    rbx
0x18000bdc2  push    rbp
0x18000bdc3  push    rsi
0x18000bdc4  push    rdi
0x18000bdc5  push    r14
0x18000bdc7  push    r15
0x18000bdc9  sub     rsp, 2A8h
0x18000bdd0  mov     rax, cs:__security_cookie
0x18000bdd7  xor     rax, rsp
0x18000bdda  mov     [rsp+2D8h+var_48], rax
0x18000bde2  mov     r8, [rcx+8]
0x18000bde6  mov     r15, rcx
0x18000bde9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bdf0  cmp     word ptr [r8+rax*2+2], 0
0x18000bdf7  lea     rax, [rax+1]
0x18000bdfb  jnz     short loc_18000BDF0
0x18000bdfd  lea     rax, ds:26h[rax*2]
0x18000be05  cmp     rax, 240h
0x18000be0b  jbe     loc_18000BEEE
0x18000be11  xor     esi, esi
0x18000be13  lea     rbx, [rsp+2D8h+Buffer]
0x18000be18  nop     dword ptr [rax+rax+00000000h]
0x18000be20  movzx   edi, word ptr [rbx]
0x18000be23  add     rbx, 2
0x18000be27  movzx   ecx, di; Source
0x18000be2a  call    cs:__imp_RtlUpcaseUnicodeChar
0x18000be30  movzx   ecx, ax
0x18000be33  imul    eax, esi, 25h ; '%'
0x18000be36  add     ecx, eax
0x18000be38  mov     esi, ecx
0x18000be3a  test    di, di
0x18000be3d  jnz     short loc_18000BE20
0x18000be3f  lea     rax, [rsp+2D8h+Buffer]
0x18000be44  sub     rbx, rax
0x18000be47  mov     eax, ecx
0x18000be49  and     eax, 7Fh
0x18000be4c  lea     rcx, qword_18003FEE8
0x18000be53  lea     rax, [rax+rax*2]
0x18000be57  lea     r14, [rcx+rax*8]
0x18000be5b  lea     rcx, [r14+10h]
0x18000be5f  call    cs:__imp_RtlAcquireSRWLockShared
0x18000be65  mov     rdi, [r14]
0x18000be68  nop     dword ptr [rax+rax+00000000h]
0x18000be70  cmp     rdi, r14
0x18000be73  jz      loc_18000C2F6
0x18000be79  cmp     rbx, [rdi-8]
0x18000be7d  lea     rsi, [rdi-18h]
0x18000be81  jz      short loc_18000BE88
0x18000be83  mov     rdi, [rdi]
0x18000be86  jmp     short loc_18000BE70
0x18000be88  mov     rcx, [rsi+8]
0x18000be8c  lea     r8, [rsp+2D8h+Buffer]
0x18000be91  mov     rdx, rbx
0x18000be94  mov     byte ptr [rsp+2D8h+var_2B8], 1
0x18000be99  shr     rdx, 1
0x18000be9c  mov     r9, rdx
0x18000be9f  call    cs:__imp_RtlCompareUnicodeStrings
0x18000bea5  test    eax, eax
0x18000bea7  jnz     short loc_18000BE83
0x18000bea9  prefetchw byte ptr [rsi]
0x18000beac  mov     eax, [rsi]
0x18000beae  test    eax, eax
0x18000beb0  jle     short loc_18000BE83
0x18000beb2  mov     edx, eax
0x18000beb4  lea     ecx, [rax+1]
0x18000beb7  lock cmpxchg [rsi], ecx
0x18000bebb  cmp     eax, edx
0x18000bebd  jnz     short loc_18000BEAE
0x18000bebf  lea     rcx, [r14+10h]
0x18000bec3  call    cs:__imp_RtlReleaseSRWLockShared
0x18000bec9  test    rsi, rsi
0x18000becc  jnz     short loc_18000BF32
0x18000bece  mov     rcx, [rsp+2D8h+var_48]
0x18000bed6  xor     rcx, rsp; StackCookie
0x18000bed9  call    __security_check_cookie
0x18000bede  add     rsp, 2A8h
0x18000bee5  pop     r15
0x18000bee7  pop     r14
0x18000bee9  pop     rdi
0x18000beea  pop     rsi
0x18000beeb  pop     rbp
0x18000beec  pop     rbx
0x18000beed  retn
0x18000beee  mov     rax, [rcx+60h]
0x18000bef2  xor     r9d, r9d
0x18000bef5  mov     [rsp+2D8h+var_298], rax
0x18000befa  lea     rcx, [rsp+2D8h+Buffer]; Buffer
0x18000beff  mov     [rsp+2D8h+var_2A0], 2Ah ; '*'
0x18000bf07  lea     rax, aWsWcI64d; "%ws%wc%I64d"
0x18000bf0e  mov     qword ptr [rsp+2D8h+Args], r8; Args
0x18000bf13  mov     edx, 240h
0x18000bf18  mov     [rsp+2D8h+Format], rax; Format
0x18000bf1d  xor     r8d, r8d
0x18000bf20  mov     [rsp+2D8h+var_2B8], 800h; int
0x18000bf28  call    RtlStringCbPrintfExW
0x18000bf2d  jmp     loc_18000BE11
0x18000bf32  movsxd  rbx, dword ptr [r15+158h]
0x18000bf39  lea     rcx, [rsi+78h]
0x18000bf3d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000bf43  mov     [rsi+84h], ebx
0x18000bf49  lea     rax, [rbx+2]
0x18000bf4d  imul    rdx, rbx, 160h
0x18000bf54  imul    rcx, rax, 160h
0x18000bf5b  mov     rax, [rcx+r15]
0x18000bf5f  mov     [rsi+rdx+88h], rax
0x18000bf67  mov     rax, [rdx+r15+0F30h]
0x18000bf6f  add     rax, [rdx+r15+2D0h]
0x18000bf77  mov     [rsi+rdx+98h], rax
0x18000bf7f  mov     rax, [rdx+r15+0F28h]
0x18000bf87  add     rax, [rdx+r15+2C8h]
0x18000bf8f  mov     [rsi+rdx+90h], rax
0x18000bf97  mov     rax, [rdx+r15+0F38h]
0x18000bf9f  add     rax, [rdx+r15+2D8h]
0x18000bfa7  mov     [rsi+rdx+0A0h], rax
0x18000bfaf  mov     rax, [rdx+r15+0F58h]
0x18000bfb7  add     rax, [rdx+r15+2F8h]
0x18000bfbf  mov     [rsi+rdx+0C0h], rax
0x18000bfc7  mov     rax, [rdx+r15+0F60h]
0x18000bfcf  add     rax, [rdx+r15+300h]
0x18000bfd7  mov     [rsi+rdx+0C8h], rax
0x18000bfdf  mov     rax, [rdx+r15+0F68h]
0x18000bfe7  add     rax, [rdx+r15+308h]
0x18000bfef  mov     [rsi+rdx+0D0h], rax
0x18000bff7  mov     rax, [rdx+r15+0F48h]
0x18000bfff  add     rax, [rdx+r15+2E8h]
0x18000c007  mov     [rsi+rdx+0B0h], rax
0x18000c00f  mov     rax, [rdx+r15+0F50h]
0x18000c017  add     rax, [rdx+r15+2F0h]
0x18000c01f  mov     [rsi+rdx+0B8h], rax
0x18000c027  mov     rax, [rdx+r15+0FB0h]
0x18000c02f  add     rax, [rdx+r15+350h]
0x18000c037  mov     [rsi+rdx+118h], rax
0x18000c03f  mov     rax, [rdx+r15+0FB8h]
0x18000c047  add     rax, [rdx+r15+358h]
0x18000c04f  mov     [rsi+rdx+120h], rax
0x18000c057  mov     rax, [rdx+r15+0FC0h]
0x18000c05f  add     rax, [rdx+r15+360h]
0x18000c067  mov     [rsi+rdx+128h], rax
0x18000c06f  mov     rax, [rdx+r15+0FC8h]
0x18000c077  add     rax, [rdx+r15+368h]
0x18000c07f  mov     [rsi+rdx+130h], rax
0x18000c087  mov     rax, [rdx+r15+0FD0h]
0x18000c08f  add     rax, [rdx+r15+370h]
0x18000c097  mov     [rsi+rdx+138h], rax
0x18000c09f  mov     rax, [rdx+r15+0F70h]
0x18000c0a7  add     rax, [rdx+r15+310h]
0x18000c0af  mov     [rsi+rdx+0D8h], rax
0x18000c0b7  mov     rax, [rdx+r15+1040h]
0x18000c0bf  add     rax, [rdx+r15+3E0h]
0x18000c0c7  mov     [rsi+rdx+1A8h], rax
0x18000c0cf  mov     rax, [rdx+r15+1000h]
0x18000c0d7  add     rax, [rdx+r15+3A0h]
0x18000c0df  mov     [rsi+rdx+168h], rax
0x18000c0e7  mov     rax, [rdx+r15+0F78h]
0x18000c0ef  add     rax, [rdx+r15+318h]
0x18000c0f7  mov     [rsi+rdx+0E0h], rax
0x18000c0ff  mov     rax, [rdx+r15+1048h]
0x18000c107  add     rax, [rdx+r15+3E8h]
0x18000c10f  mov     [rsi+rdx+1B0h], rax
0x18000c117  mov     rax, [rdx+r15+1008h]
0x18000c11f  add     rax, [rdx+r15+3A8h]
0x18000c127  mov     [rsi+rdx+170h], rax
0x18000c12f  mov     rax, [rdx+r15+0F80h]
0x18000c137  add     rax, [rdx+r15+320h]
0x18000c13f  mov     [rsi+rdx+0E8h], rax
0x18000c147  mov     rax, [rdx+r15+1050h]
0x18000c14f  add     rax, [rdx+r15+3F0h]
0x18000c157  mov     [rsi+rdx+1B8h], rax
0x18000c15f  mov     rax, [rdx+r15+1010h]
0x18000c167  add     rax, [rdx+r15+3B0h]
0x18000c16f  mov     [rsi+rdx+178h], rax
0x18000c177  mov     rax, [rdx+r15+0F88h]
0x18000c17f  add     rax, [rdx+r15+328h]
0x18000c187  mov     [rsi+rdx+0F0h], rax
0x18000c18f  mov     rax, [rdx+r15+1058h]
0x18000c197  add     rax, [rdx+r15+3F8h]
0x18000c19f  mov     [rsi+rdx+1C0h], rax
0x18000c1a7  mov     rax, [rdx+r15+1018h]
0x18000c1af  lea     rcx, [rsi+78h]
0x18000c1b3  add     rax, [rdx+r15+3B8h]
0x18000c1bb  mov     [rsi+rdx+180h], rax
0x18000c1c3  mov     rax, [rdx+r15+0F90h]
0x18000c1cb  add     rax, [rdx+r15+330h]
0x18000c1d3  mov     [rsi+rdx+0F8h], rax
0x18000c1db  mov     rax, [rdx+r15+1060h]
0x18000c1e3  add     rax, [rdx+r15+400h]
0x18000c1eb  mov     [rsi+rdx+1C8h], rax
0x18000c1f3  mov     rax, [rdx+r15+1020h]
0x18000c1fb  add     rax, [rdx+r15+3C0h]
0x18000c203  mov     [rsi+rdx+188h], rax
0x18000c20b  mov     rax, [rdx+r15+0F98h]
0x18000c213  add     rax, [rdx+r15+338h]
0x18000c21b  mov     [rsi+rdx+100h], rax
0x18000c223  mov     rax, [rdx+r15+1068h]
0x18000c22b  add     rax, [rdx+r15+408h]
0x18000c233  mov     [rsi+rdx+1D0h], rax
0x18000c23b  mov     rax, [rdx+r15+1028h]
0x18000c243  add     rax, [rdx+r15+3C8h]
0x18000c24b  mov     [rsi+rdx+190h], rax
0x18000c253  mov     rax, [rdx+r15+0FA0h]
0x18000c25b  add     rax, [rdx+r15+340h]
0x18000c263  mov     [rsi+rdx+108h], rax
0x18000c26b  mov     rax, [rdx+r15+1070h]
0x18000c273  add     rax, [rdx+r15+410h]
0x18000c27b  mov     [rsi+rdx+1D8h], rax
0x18000c283  mov     rax, [rdx+r15+1030h]
0x18000c28b  add     rax, [rdx+r15+3D0h]
0x18000c293  mov     [rsi+rdx+198h], rax
0x18000c29b  mov     rax, [rdx+r15+0FA8h]
0x18000c2a3  add     rax, [rdx+r15+348h]
0x18000c2ab  mov     [rsi+rdx+110h], rax
0x18000c2b3  mov     rax, [rdx+r15+1078h]
0x18000c2bb  add     rax, [rdx+r15+418h]
0x18000c2c3  mov     [rsi+rdx+1E0h], rax
0x18000c2cb  mov     rax, [rdx+r15+1038h]
0x18000c2d3  add     rax, [rdx+r15+3D8h]
0x18000c2db  mov     [rsi+rdx+1A0h], rax
0x18000c2e3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c2e9  mov     rcx, rsi
0x18000c2ec  call    PsmpDereferenceAppUsageInfo
0x18000c2f1  jmp     loc_18000BECE
0x18000c2f6  lea     rcx, [r14+10h]
0x18000c2fa  call    cs:__imp_RtlReleaseSRWLockShared
0x18000c300  jmp     loc_18000BECE
```
