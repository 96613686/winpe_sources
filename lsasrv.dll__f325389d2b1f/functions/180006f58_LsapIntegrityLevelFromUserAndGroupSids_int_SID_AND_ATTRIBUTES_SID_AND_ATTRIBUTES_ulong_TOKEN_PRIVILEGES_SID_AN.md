# LsapIntegrityLevelFromUserAndGroupSids(int,_SID_AND_ATTRIBUTES *,_SID_AND_ATTRIBUTES *,ulong,_TOKEN_PRIVILEGES *,_SID_AND_ATTRIBUTES *)

- ea: `0x180006f58`
- end: `0x180007261`
- name: `?LsapIntegrityLevelFromUserAndGroupSids@@YAJHPEAU_SID_AND_ATTRIBUTES@@0KPEAU_TOKEN_PRIVILEGES@@0@Z`
- size: `777`
- prototype: `__int64 __fastcall(int, struct _SID_AND_ATTRIBUTES *, struct _SID_AND_ATTRIBUTES *, unsigned int, struct _TOKEN_PRIVILEGES *, struct _SID_AND_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006240`

## callees

- `0x180006f58`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `ntdll!RtlSidHashInitialize` at `0x180006fab`
- `ntdll!RtlSidHashInitialize` at `0x180006fab`
- `ntdll!RtlSidHashLookup` at `0x180006fcf`
- `ntdll!RtlSidHashLookup` at `0x180006ff0`
- `ntdll!RtlSidHashLookup` at `0x180007011`
- `ntdll!RtlSidHashLookup` at `0x180007032`
- `ntdll!RtlSidHashLookup` at `0x180007053`
- `ntdll!RtlSidHashLookup` at `0x1800070a8`
- `ntdll!RtlSidHashLookup` at `0x180007147`
- `ntdll!RtlSidHashLookup` at `0x18000718f`
- `ntdll!RtlSidHashLookup` at `0x180006fcf`
- `ntdll!RtlSidHashLookup` at `0x180006ff0`
- `ntdll!RtlSidHashLookup` at `0x180007011`
- `ntdll!RtlSidHashLookup` at `0x180007032`
- `ntdll!RtlSidHashLookup` at `0x180007053`
- `ntdll!RtlSidHashLookup` at `0x1800070a8`
- `ntdll!RtlSidHashLookup` at `0x180007147`
- `ntdll!RtlSidHashLookup` at `0x18000718f`
- `ntdll!RtlEqualSid` at `0x1800070d6`
- `ntdll!RtlEqualSid` at `0x1800071bd`
- `ntdll!RtlEqualSid` at `0x1800071fa`
- `ntdll!RtlEqualSid` at `0x1800070d6`
- `ntdll!RtlEqualSid` at `0x1800071bd`
- `ntdll!RtlEqualSid` at `0x1800071fa`

## pseudocode

```c
__int64 __fastcall LsapIntegrityLevelFromUserAndGroupSids(
        int a1,
        struct _SID_AND_ATTRIBUTES *a2,
        struct _SID_AND_ATTRIBUTES *a3,
        unsigned int a4,
        struct _TOKEN_PRIVILEGES *a5,
        struct _SID_AND_ATTRIBUTES *a6)
{
  int v10; // ebp
  void *v11; // rbx
  __int64 i; // rdi
  __int64 k; // rdi
  __int64 j; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  DWORD LowPart; // r10d
  _BYTE v19[272]; // [rsp+20h] [rbp-158h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v10 = RtlSidHashInitialize(a3, a4, v19);
  if ( v10 >= 0 )
  {
    v11 = 0;
    if ( !RtlSidHashLookup(v19, qword_18019ED70)
      && !RtlSidHashLookup(v19, qword_18019ED60)
      && !RtlSidHashLookup(v19, qword_18019ED50)
      && !RtlSidHashLookup(v19, qword_18019ED40)
      && !RtlSidHashLookup(v19, *(_QWORD *)&MandatorySids.Revision) )
    {
      v11 = *(void **)&MandatorySids.Revision;
      if ( !a1 )
      {
        for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
        {
          if ( RtlSidHashLookup(v19, *((_QWORD *)WellKnownSids + 6 * *((unsigned int *)&SystemIntegritySidIndices + i)))
            || RtlEqualSid(a2->Sid, *((PSID *)WellKnownSids + 6 * *((unsigned int *)&SystemIntegritySidIndices + i))) )
          {
            v11 = (void *)qword_18019ED70;
            goto LABEL_14;
          }
        }
        for ( j = 0; !(_DWORD)j; j = 1 )
        {
          if ( RtlSidHashLookup(v19, *((_QWORD *)WellKnownSids + 6 * *((unsigned int *)&HighIntegritySidIndices + j)))
            || RtlEqualSid(a2->Sid, *((PSID *)WellKnownSids + 6 * *((unsigned int *)&HighIntegritySidIndices + j))) )
          {
            goto LABEL_25;
          }
        }
        v16 = 0;
        v17 = 0;
        if ( a5->PrivilegeCount )
        {
          do
          {
            LowPart = a5->Privileges[v17].Luid.LowPart;
            if ( LowPart - 2 <= 0x22 )
              v16 |= 1LL << LowPart;
            v17 = (unsigned int)(v17 + 1);
          }
          while ( (unsigned int)v17 < a5->PrivilegeCount );
          if ( (v16 & 0x1120160684LL) != 0 )
          {
LABEL_25:
            v11 = (void *)qword_18019ED60;
            goto LABEL_14;
          }
        }
      }
      for ( k = 0; (unsigned int)k < 2; k = (unsigned int)(k + 1) )
      {
        if ( RtlSidHashLookup(v19, *((_QWORD *)WellKnownSids + 6 * *((unsigned int *)&MediumIntegritySidIndices + k)))
          || RtlEqualSid(a2->Sid, *((PSID *)WellKnownSids + 6 * *((unsigned int *)&MediumIntegritySidIndices + k))) )
        {
          v11 = (void *)qword_18019ED50;
          break;
        }
      }
    }
LABEL_14:
    a6->Sid = v11;
    a6->Attributes = 96;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006f58  push    rbx
0x180006f5a  push    rbp
0x180006f5b  push    rsi
0x180006f5c  push    rdi
0x180006f5d  push    r12
0x180006f5f  push    r14
0x180006f61  push    r15
0x180006f63  sub     rsp, 140h
0x180006f6a  mov     rax, cs:__security_cookie
0x180006f71  xor     rax, rsp
0x180006f74  mov     [rsp+178h+var_48], rax
0x180006f7c  mov     r14, [rsp+178h+arg_28]
0x180006f84  mov     rbx, r8
0x180006f87  mov     r15, rdx
0x180006f8a  mov     esi, ecx
0x180006f8c  xor     edx, edx; Val
0x180006f8e  lea     rcx, [rsp+178h+var_158]; void *
0x180006f93  mov     r8d, 110h; Size
0x180006f99  mov     edi, r9d
0x180006f9c  call    memset_0
0x180006fa1  lea     r8, [rsp+178h+var_158]
0x180006fa6  mov     edx, edi
0x180006fa8  mov     rcx, rbx
0x180006fab  call    cs:__imp_RtlSidHashInitialize
0x180006fb2  nop     dword ptr [rax+rax+00h]
0x180006fb7  mov     ebp, eax
0x180006fb9  test    eax, eax
0x180006fbb  js      loc_1800070FC
0x180006fc1  mov     rdx, cs:qword_18019ED70
0x180006fc8  lea     rcx, [rsp+178h+var_158]
0x180006fcd  xor     ebx, ebx
0x180006fcf  call    cs:__imp_RtlSidHashLookup
0x180006fd6  nop     dword ptr [rax+rax+00h]
0x180006fdb  test    rax, rax
0x180006fde  jnz     loc_1800070F1
0x180006fe4  mov     rdx, cs:qword_18019ED60
0x180006feb  lea     rcx, [rsp+178h+var_158]
0x180006ff0  call    cs:__imp_RtlSidHashLookup
0x180006ff7  nop     dword ptr [rax+rax+00h]
0x180006ffc  test    rax, rax
0x180006fff  jnz     loc_1800070F1
0x180007005  mov     rdx, cs:qword_18019ED50
0x18000700c  lea     rcx, [rsp+178h+var_158]
0x180007011  call    cs:__imp_RtlSidHashLookup
0x180007018  nop     dword ptr [rax+rax+00h]
0x18000701d  test    rax, rax
0x180007020  jnz     loc_1800070F1
0x180007026  mov     rdx, cs:qword_18019ED40
0x18000702d  lea     rcx, [rsp+178h+var_158]
0x180007032  call    cs:__imp_RtlSidHashLookup
0x180007039  nop     dword ptr [rax+rax+00h]
0x18000703e  test    rax, rax
0x180007041  jnz     loc_1800070F1
0x180007047  mov     rdx, qword ptr cs:?MandatorySids@@3PAU_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES near * MandatorySids ...
0x18000704e  lea     rcx, [rsp+178h+var_158]
0x180007053  call    cs:__imp_RtlSidHashLookup
0x18000705a  nop     dword ptr [rax+rax+00h]
0x18000705f  test    rax, rax
0x180007062  jnz     loc_1800070F1
0x180007068  mov     rbx, qword ptr cs:?MandatorySids@@3PAU_SID_AND_ATTRIBUTES@@A.Revision; _SID_AND_ATTRIBUTES near * MandatorySids ...
0x18000706f  lea     r12, __ImageBase
0x180007076  test    esi, esi
0x180007078  jnz     loc_180007121
0x18000707e  xor     edi, edi
0x180007080  cmp     edi, 3
0x180007083  jnb     loc_180007165
0x180007089  mov     eax, ds:rva ?SystemIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * SystemIntegritySidIndices ...
0x180007091  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180007098  lea     rcx, [rax+rax*2]
0x18000709c  add     rcx, rcx
0x18000709f  mov     rdx, [rdx+rcx*8]
0x1800070a3  lea     rcx, [rsp+178h+var_158]
0x1800070a8  call    cs:__imp_RtlSidHashLookup
0x1800070af  nop     dword ptr [rax+rax+00h]
0x1800070b4  test    rax, rax
0x1800070b7  jnz     short loc_1800070EA
0x1800070b9  mov     eax, ds:rva ?SystemIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * SystemIntegritySidIndices ...
0x1800070c1  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800070c8  lea     rcx, [rax+rax*2]
0x1800070cc  add     rcx, rcx
0x1800070cf  mov     rdx, [rdx+rcx*8]; Sid2
0x1800070d3  mov     rcx, [r15]; Sid1
0x1800070d6  call    cs:__imp_RtlEqualSid
0x1800070dd  nop     dword ptr [rax+rax+00h]
0x1800070e2  test    al, al
0x1800070e4  jnz     short loc_1800070EA
0x1800070e6  inc     edi
0x1800070e8  jmp     short loc_180007080
0x1800070ea  mov     rbx, cs:qword_18019ED70
0x1800070f1  mov     [r14], rbx
0x1800070f4  mov     dword ptr [r14+8], 60h ; '`'
0x1800070fc  mov     eax, ebp
0x1800070fe  mov     rcx, [rsp+178h+var_48]
0x180007106  xor     rcx, rsp; StackCookie
0x180007109  call    __security_check_cookie
0x18000710e  add     rsp, 140h
0x180007115  pop     r15
0x180007117  pop     r14
0x180007119  pop     r12
0x18000711b  pop     rdi
0x18000711c  pop     rsi
0x18000711d  pop     rbp
0x18000711e  pop     rbx
0x18000711f  retn
0x180007121  xor     edi, edi
0x180007123  cmp     edi, 2
0x180007126  jnb     short loc_1800070F1
0x180007128  mov     eax, ds:rva ?MediumIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * MediumIntegritySidIndices ...
0x180007130  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180007137  lea     rcx, [rax+rax*2]
0x18000713b  add     rcx, rcx
0x18000713e  mov     rdx, [rdx+rcx*8]
0x180007142  lea     rcx, [rsp+178h+var_158]
0x180007147  call    cs:__imp_RtlSidHashLookup
0x18000714e  nop     dword ptr [rax+rax+00h]
0x180007153  test    rax, rax
0x180007156  jz      loc_1800071DD
0x18000715c  mov     rbx, cs:qword_18019ED50
0x180007163  jmp     short loc_1800070F1
0x180007165  xor     edi, edi
0x180007167  cmp     edi, 1
0x18000716a  jnb     loc_180007215
0x180007170  mov     eax, ds:rva ?HighIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * HighIntegritySidIndices ...
0x180007178  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18000717f  lea     rcx, [rax+rax*2]
0x180007183  add     rcx, rcx
0x180007186  mov     rdx, [rdx+rcx*8]
0x18000718a  lea     rcx, [rsp+178h+var_158]
0x18000718f  call    cs:__imp_RtlSidHashLookup
0x180007196  nop     dword ptr [rax+rax+00h]
0x18000719b  test    rax, rax
0x18000719e  jnz     short loc_1800071D1
0x1800071a0  mov     eax, ds:rva ?HighIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * HighIntegritySidIndices ...
0x1800071a8  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800071af  lea     rcx, [rax+rax*2]
0x1800071b3  add     rcx, rcx
0x1800071b6  mov     rdx, [rdx+rcx*8]; Sid2
0x1800071ba  mov     rcx, [r15]; Sid1
0x1800071bd  call    cs:__imp_RtlEqualSid
0x1800071c4  nop     dword ptr [rax+rax+00h]
0x1800071c9  test    al, al
0x1800071cb  jnz     short loc_1800071D1
0x1800071cd  inc     edi
0x1800071cf  jmp     short loc_180007167
0x1800071d1  mov     rbx, cs:qword_18019ED60
0x1800071d8  jmp     loc_1800070F1
0x1800071dd  mov     eax, ds:rva ?MediumIntegritySidIndices@@3PAKA[r12+rdi*4]; ulong near * MediumIntegritySidIndices ...
0x1800071e5  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800071ec  lea     rcx, [rax+rax*2]
0x1800071f0  add     rcx, rcx
0x1800071f3  mov     rdx, [rdx+rcx*8]; Sid2
0x1800071f7  mov     rcx, [r15]; Sid1
0x1800071fa  call    cs:__imp_RtlEqualSid
0x180007201  nop     dword ptr [rax+rax+00h]
0x180007206  test    al, al
0x180007208  jnz     loc_18000715C
0x18000720e  inc     edi
0x180007210  jmp     loc_180007123
0x180007215  mov     r9, [rsp+178h+arg_20]
0x18000721d  xor     edx, edx
0x18000721f  xor     r8d, r8d
0x180007222  cmp     [r9], edx
0x180007225  jbe     loc_180007121
0x18000722b  lea     rcx, [r8+r8*2]
0x18000722f  mov     r10d, [r9+rcx*4+4]
0x180007234  lea     eax, [r10-2]
0x180007238  cmp     eax, 22h ; '"'
0x18000723b  ja      short loc_180007241
0x18000723d  bts     rdx, r10
0x180007241  inc     r8d
0x180007244  cmp     r8d, [r9]
0x180007247  jb      short loc_18000722B
0x180007249  mov     rax, 1120160684h
0x180007253  test    rax, rdx
0x180007256  jnz     loc_1800071D1
0x18000725c  jmp     loc_180007121
```
