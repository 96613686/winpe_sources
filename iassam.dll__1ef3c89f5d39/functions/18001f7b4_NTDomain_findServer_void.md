# NTDomain::findServer(void)

- ea: `0x18001f7b4`
- end: `0x18001f9a7`
- name: `?findServer@NTDomain@@IEAAXXZ`
- size: `499`
- prototype: `void __fastcall(NTDomain *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001df3c`
- `0x18001f9b0`

## callees

- `0x18000c4a4`
- `0x180018218`
- `0x18001f7b4`
- `0x180020028`
- `0x1800200f4`
- `0x1800254a0`

## import_xrefs

- `iassvcs!IASReportEvent` at `0x18001f8f1`
- `iassvcs!IASReportEvent` at `0x18001f985`
- `iassvcs!IASReportEvent` at `0x18001f8f1`
- `iassvcs!IASReportEvent` at `0x18001f985`

## string_xrefs

- `0x18001f805`: `Failed to connect to the cached DC, try DC locator ...`

## pseudocode

```c
void __fastcall NTDomain::findServer(NTDomain *this)
{
  char v2; // di
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD v5; // eax
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = NTDomain::tryNearestDomainController(this, 1, *((_DWORD *)this + 32));
  *((_DWORD *)this + 32) = v3;
  if ( !v3 )
    goto LABEL_22;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Failed to connect to the cached DC, try DC locator ...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids, "NPSSVC");
  }
  v4 = NTDomain::tryNearestDomainController(this, 0, *((_DWORD *)this + 32));
  *((_DWORD *)this + 32) = v4;
  if ( !v4 )
    goto LABEL_22;
  if ( v4 == 1212 || v4 == 1355 || v4 == 8200 )
    goto LABEL_15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Failed to connect to the DC discovered by DC locator, try DC enumerator ...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids, "NPSSVC");
  }
  v5 = NTDomain::tryAllDomainControllers(this);
  *((_DWORD *)this + 32) = v5;
  v2 = 1;
  if ( v5 )
  {
LABEL_15:
    v6 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) >= 8u )
      v6 = (_QWORD *)*v6;
    v11 = v6;
    IASReportEvent(3221229874LL, 1, 0, &v11, 0);
    if ( *((_DWORD *)this + 32) != 8200 )
    {
      v7 = GetSystemTimeAsDWORDLONG() + 600000000;
      goto LABEL_20;
    }
    *((_DWORD *)this + 28) = 1;
  }
  else
  {
LABEL_22:
    v8 = (_QWORD *)(*((_QWORD *)this + 15) + 56LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 15) + 80LL) >= 8u )
      v8 = (_QWORD *)*v8;
    v10[0] = v8;
    v9 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) >= 8u )
      v9 = (_QWORD *)*v9;
    v10[1] = v9;
    IASReportEvent(1073746224, 2, 0, v10, 0);
    if ( *((_DWORD *)this + 28) == 3 && !v2 )
    {
      v7 = -1;
      goto LABEL_20;
    }
  }
  v7 = GetSystemTimeAsDWORDLONG() + 36000000000LL;
LABEL_20:
  *((_QWORD *)this + 17) = v7;
}

```

## disassembly

```asm
0x18001f7b4  mov     [rsp+arg_8], rbx
0x18001f7b9  mov     [rsp+arg_10], rdi
0x18001f7be  push    r14
0x18001f7c0  sub     rsp, 40h
0x18001f7c4  mov     rbx, rcx
0x18001f7c7  xor     dil, dil
0x18001f7ca  mov     r8d, [rcx+80h]; unsigned int
0x18001f7d1  mov     dl, 1; bool
0x18001f7d3  call    ?tryNearestDomainController@NTDomain@@AEAAK_NK@Z; NTDomain::tryNearestDomainController(bool,ulong)
0x18001f7d8  mov     [rbx+80h], eax
0x18001f7de  test    eax, eax
0x18001f7e0  jz      loc_18001F941
0x18001f7e6  lea     r14, WPP_GLOBAL_Control
0x18001f7ed  mov     rax, cs:WPP_GLOBAL_Control
0x18001f7f4  cmp     rax, r14
0x18001f7f7  jz      short loc_18001F834
0x18001f7f9  cmp     byte ptr [rax+19h], 2
0x18001f7fd  jb      short loc_18001F834
0x18001f7ff  test    byte ptr [rax+1Ch], 4
0x18001f803  jz      short loc_18001F834
0x18001f805  lea     rcx, aFailedToConnec_0; "Failed to connect to the cached DC, try"...
0x18001f80c  call    WppDbgPrint
0x18001f811  mov     edx, 0Fh
0x18001f816  lea     r9, aNpssvc; "NPSSVC"
0x18001f81d  lea     r8, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids
0x18001f824  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f82b  mov     rcx, [rcx+10h]
0x18001f82f  call    WPP_SF_s
0x18001f834  mov     r8d, [rbx+80h]; unsigned int
0x18001f83b  xor     edx, edx; bool
0x18001f83d  mov     rcx, rbx; this
0x18001f840  call    ?tryNearestDomainController@NTDomain@@AEAAK_NK@Z; NTDomain::tryNearestDomainController(bool,ulong)
0x18001f845  mov     [rbx+80h], eax
0x18001f84b  test    eax, eax
0x18001f84d  jz      loc_18001F941
0x18001f853  cmp     eax, 4BCh
0x18001f858  jz      short loc_18001F8C4
0x18001f85a  cmp     eax, 54Bh
0x18001f85f  jz      short loc_18001F8C4
0x18001f861  cmp     eax, 2008h
0x18001f866  jz      short loc_18001F8C4
0x18001f868  mov     rax, cs:WPP_GLOBAL_Control
0x18001f86f  cmp     rax, r14
0x18001f872  jz      short loc_18001F8AF
0x18001f874  cmp     byte ptr [rax+19h], 2
0x18001f878  jb      short loc_18001F8AF
0x18001f87a  test    byte ptr [rax+1Ch], 4
0x18001f87e  jz      short loc_18001F8AF
0x18001f880  lea     rcx, aFailedToConnec; "Failed to connect to the DC discovered "...
0x18001f887  call    WppDbgPrint
0x18001f88c  mov     edx, 10h
0x18001f891  lea     r9, aNpssvc; "NPSSVC"
0x18001f898  lea     r8, WPP_3d17ec2a460a38aa7d49725326c61fb2_Traceguids
0x18001f89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a6  mov     rcx, [rcx+10h]
0x18001f8aa  call    WPP_SF_s
0x18001f8af  mov     rcx, rbx; this
0x18001f8b2  call    ?tryAllDomainControllers@NTDomain@@AEAAKXZ; NTDomain::tryAllDomainControllers(void)
0x18001f8b7  mov     [rbx+80h], eax
0x18001f8bd  mov     dil, 1
0x18001f8c0  test    eax, eax
0x18001f8c2  jz      short loc_18001F941
0x18001f8c4  lea     rax, [rbx+30h]
0x18001f8c8  cmp     qword ptr [rax+18h], 8
0x18001f8cd  jb      short loc_18001F8D2
0x18001f8cf  mov     rax, [rax]
0x18001f8d2  mov     [rsp+48h+arg_0], rax
0x18001f8d7  mov     [rsp+48h+var_28], 0
0x18001f8e0  lea     r9, [rsp+48h+arg_0]
0x18001f8e5  xor     r8d, r8d
0x18001f8e8  lea     edx, [r8+1]
0x18001f8ec  mov     ecx, 0C0001132h
0x18001f8f1  call    cs:__imp_IASReportEvent
0x18001f8f7  cmp     dword ptr [rbx+80h], 2008h
0x18001f901  jnz     short loc_18001F934
0x18001f903  mov     dword ptr [rbx+70h], 1
0x18001f90a  call    GetSystemTimeAsDWORDLONG
0x18001f90f  mov     rcx, 861C46800h
0x18001f919  add     rax, rcx
0x18001f91c  mov     [rbx+88h], rax
0x18001f923  mov     rbx, [rsp+48h+arg_8]
0x18001f928  mov     rdi, [rsp+48h+arg_10]
0x18001f92d  add     rsp, 40h
0x18001f931  pop     r14
0x18001f933  retn
0x18001f934  call    GetSystemTimeAsDWORDLONG
0x18001f939  add     rax, 23C34600h
0x18001f93f  jmp     short loc_18001F91C
0x18001f941  mov     rax, [rbx+78h]
0x18001f945  add     rax, 38h ; '8'
0x18001f949  cmp     qword ptr [rax+18h], 8
0x18001f94e  jb      short loc_18001F953
0x18001f950  mov     rax, [rax]
0x18001f953  mov     [rsp+48h+var_18], rax
0x18001f958  lea     rax, [rbx+30h]
0x18001f95c  cmp     qword ptr [rax+18h], 8
0x18001f961  jb      short loc_18001F966
0x18001f963  mov     rax, [rax]
0x18001f966  mov     [rsp+48h+var_10], rax
0x18001f96b  mov     [rsp+48h+var_28], 0
0x18001f974  lea     r9, [rsp+48h+var_18]
0x18001f979  xor     r8d, r8d
0x18001f97c  lea     edx, [r8+2]
0x18001f980  mov     ecx, 40001130h
0x18001f985  call    cs:__imp_IASReportEvent
0x18001f98b  cmp     dword ptr [rbx+70h], 3
0x18001f98f  jnz     loc_18001F90A
0x18001f995  test    dil, dil
0x18001f998  jnz     loc_18001F90A
0x18001f99e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f9a2  jmp     loc_18001F91C
```
