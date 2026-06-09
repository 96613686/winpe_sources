# ParseServiceURL(ushort const *,ulong *,ushort * *,ushort * *,int)

- ea: `0x18001d684`
- end: `0x18001db00`
- name: `?ParseServiceURL@@YAJPEBGPEAKPEAPEAG2H@Z`
- size: `1148`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, unsigned __int16 **, unsigned __int16 **, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d370`
- `0x18001436c`
- `0x180019b38`
- `0x18001a2cc`
- `0x18002f1c4`
- `0x18002f6bc`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000bd08`
- `0x1800141b0`
- `0x180014b6c`
- `0x18001d684`
- `0x18004b910`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d7d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d7f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d7d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d7f7`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d8c5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d8c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d7b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d81a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d9ae`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d7b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d81a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18001d9ae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d8ac`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d8ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d95e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001da81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d95e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001da81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d947`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d947`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da6a`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x18001d845`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x18001d845`

## string_xrefs

- `0x18001d6f5`: `ParseServiceURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParseServiceURL(wchar_t *a1, unsigned int *a2, unsigned __int16 **a3, unsigned __int16 **a4, int a5)
{
  __int64 v9; // rcx
  __int64 v10; // rdx
  wchar_t *v11; // rax
  wchar_t v12; // r8
  wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // rbx
  int v16; // r14d
  BOOL v17; // edi
  int v18; // eax
  int v19; // esi
  int IsLockedToMmpc; // eax
  wchar_t *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  wchar_t *v24; // rax
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v28; // rax
  __int64 v30; // r8
  wchar_t *v31; // rax
  const WCHAR *v32; // rax
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rdi
  HANDLE v35; // rax
  unsigned __int16 *v36; // rax
  const unsigned __int16 *v37; // r8
  unsigned int v38; // ebx
  __int64 v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Delimiter[2]; // [rsp+2Ch] [rbp-D4h] BYREF
  int v43; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v44[2]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t *Context; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v46[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t String[2088]; // [rsp+50h] [rbp-B0h] BYREF

  LODWORD(v40) = 0;
  memset_0(String, 0, 0x1048u);
  wcscpy(Delimiter, L"/");
  wcscpy(v44, L" ");
  Context = 0;
  v46[0] = "ParseServiceURL";
  v46[1] = &v40;
  if ( !a1 )
  {
    LODWORD(v40) = -2147024809;
    goto LABEL_59;
  }
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v41 = 0;
  LODWORD(v40) = Mmpc_IsOnPremiseSupportingDevice(&v41);
  if ( (int)v40 >= 0 )
  {
    v9 = 2147483646;
    v10 = 2084;
    v11 = String;
    do
    {
      if ( !v9 )
        break;
      v12 = *a1;
      if ( !*a1 )
        break;
      ++a1;
      *v11++ = v12;
      --v9;
      --v10;
    }
    while ( v10 );
    v13 = v11 - 1;
    if ( v10 )
      v13 = v11;
    *v13 = 0;
    LODWORD(v40) = v10 == 0 ? 0x8007007A : 0;
    if ( v10 )
    {
      v14 = wcstok_s(String, Delimiter, &Context);
      v15 = v14;
      if ( v14 )
      {
        v16 = _o__wcsicmp(v14, L"http:");
        v17 = v16 == 0;
        v18 = _o__wcsicmp(v15, L"https:");
        v19 = v18;
        if ( !v16 || !v18 )
        {
          v15 = wcstok_s(0, Delimiter, &Context);
          *a2 = v19 != 0 ? 80 : 443;
        }
        v43 = 0;
        IsLockedToMmpc = Mmpc_Lockdown_IsLockedToMmpc(&v43);
        LODWORD(v40) = IsLockedToMmpc;
        if ( IsLockedToMmpc == -2147024769 )
        {
          LODWORD(v40) = 0;
        }
        else if ( IsLockedToMmpc < 0 )
        {
          goto LABEL_59;
        }
        if ( !v16 && (v43 || v41) )
          v17 = 0;
        dword_1800706BC = !v17;
      }
      if ( v15 )
      {
        v21 = wcschr(v15, 0x3Au);
        if ( v21 )
        {
          *v21 = 0;
          v22 = _o__wtoi(v21 + 1);
          *a2 = v22;
          if ( !v22 )
            goto LABEL_59;
        }
        v23 = 0x7FFFFFFF;
        v24 = v15;
        do
        {
          if ( !*v24 )
            break;
          ++v24;
          --v23;
        }
        while ( v23 );
        v25 = (0x7FFFFFFF - v23) & -(__int64)(v23 != 0);
        LODWORD(v40) = v23 == 0 ? 0x80070057 : 0;
        if ( !v23 )
          goto LABEL_59;
        v26 = v25 + 1;
        if ( v25 + 1 < v25 )
          goto LABEL_58;
        v40 = 0;
        if ( !is_mul_ok(v26, 2u) )
          goto LABEL_58;
        LODWORD(v40) = 0;
        ProcessHeap = GetProcessHeap();
        v28 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v26);
        *a3 = v28;
        if ( !v28 )
        {
          LODWORD(v40) = -2147024882;
          goto LABEL_59;
        }
        LODWORD(v40) = 0;
        LODWORD(v40) = StringCchCopyW(v28, v26, v15);
        if ( (int)v40 < 0 )
          goto LABEL_59;
        v15 = wcstok_s(0, v44, &Context);
      }
      if ( v41 )
        a5 = 0;
      if ( v15 )
      {
        v30 = 0x7FFFFFFF;
        v31 = v15;
        do
        {
          if ( !*v31 )
            break;
          ++v31;
          --v30;
        }
        while ( v30 );
      }
      else
      {
        if ( !a5 )
          goto LABEL_59;
        v30 = 0x7FFFFFFF;
        v32 = L"EnrollmentServer/Discovery.svc";
        do
        {
          if ( !*v32 )
            break;
          ++v32;
          --v30;
        }
        while ( v30 );
      }
      v33 = (0x7FFFFFFF - v30) & -(__int64)(v30 != 0);
      LODWORD(v40) = v30 == 0 ? 0x80070057 : 0;
      if ( !v30 )
        goto LABEL_59;
      v34 = v33 + 1;
      if ( v33 + 1 >= v33 )
      {
        v40 = 0;
        if ( is_mul_ok(v34, 2u) )
        {
          LODWORD(v40) = 0;
          if ( a4 )
          {
            v35 = GetProcessHeap();
            v36 = (unsigned __int16 *)HeapAlloc(v35, 8u, 2 * v34);
            *a4 = v36;
            LODWORD(v40) = 0;
            if ( v15 )
            {
              v37 = v15;
            }
            else
            {
              if ( !a5 )
                goto LABEL_59;
              v37 = L"EnrollmentServer/Discovery.svc";
            }
            LODWORD(v40) = StringCchCopyW(v36, v34, v37);
          }
          goto LABEL_59;
        }
      }
LABEL_58:
      LODWORD(v40) = -2147024362;
    }
  }
LABEL_59:
  v38 = v40;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v46);
  return v38;
}

```

## disassembly

```asm
0x18001d684  mov     [rsp-8+arg_0], rbx
0x18001d689  push    rbp
0x18001d68a  push    rsi
0x18001d68b  push    rdi
0x18001d68c  push    r12
0x18001d68e  push    r13
0x18001d690  push    r14
0x18001d692  push    r15
0x18001d694  lea     rbp, [rsp-0FB0h]
0x18001d69c  mov     eax, 10B0h
0x18001d6a1  call    _alloca_probe
0x18001d6a6  sub     rsp, rax
0x18001d6a9  mov     rax, cs:__security_cookie
0x18001d6b0  xor     rax, rsp
0x18001d6b3  mov     [rbp+0FE0h+var_40], rax
0x18001d6ba  mov     r12, r9
0x18001d6bd  mov     r13, r8
0x18001d6c0  mov     r15, rdx
0x18001d6c3  mov     rbx, rcx
0x18001d6c6  xor     r14d, r14d
0x18001d6c9  mov     dword ptr [rsp+10E0h+var_10C0], r14d
0x18001d6ce  xor     edx, edx; Val
0x18001d6d0  mov     r8d, 1048h; Size
0x18001d6d6  lea     rcx, [rsp+10E0h+String]; void *
0x18001d6db  call    memset_0
0x18001d6e0  mov     dword ptr [rsp+10E0h+Delimiter], 2Fh ; '/'
0x18001d6e8  mov     dword ptr [rsp+10E0h+var_10AC], 20h ; ' '
0x18001d6f0  mov     [rsp+10E0h+Context], r14
0x18001d6f5  lea     rax, aParseserviceur; "ParseServiceURL"
0x18001d6fc  mov     [rsp+10E0h+var_10A0], rax
0x18001d701  lea     rax, [rsp+10E0h+var_10C0]
0x18001d706  mov     [rsp+10E0h+var_1098], rax
0x18001d70b  test    rbx, rbx
0x18001d70e  jnz     short loc_18001D71E
0x18001d710  mov     esi, 80070057h
0x18001d715  mov     dword ptr [rsp+10E0h+var_10C0], esi
0x18001d719  jmp     loc_18001DAC5
0x18001d71e  mov     [r13+0], r14
0x18001d722  test    r12, r12
0x18001d725  jz      short loc_18001D72B
0x18001d727  mov     [r12], r14
0x18001d72b  mov     [rsp+10E0h+var_10B8], r14d
0x18001d730  lea     rcx, [rsp+10E0h+var_10B8]; int *
0x18001d735  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x18001d73a  mov     dword ptr [rsp+10E0h+var_10C0], eax
0x18001d73e  test    eax, eax
0x18001d740  js      loc_18001DAC5
0x18001d746  mov     ecx, 7FFFFFFEh
0x18001d74b  mov     edx, 824h
0x18001d750  lea     rax, [rsp+10E0h+String]
0x18001d755  test    rcx, rcx
0x18001d758  jz      short loc_18001D779
0x18001d75a  movzx   r8d, word ptr [rbx]
0x18001d75e  test    r8w, r8w
0x18001d762  jz      short loc_18001D779
0x18001d764  add     rbx, 2
0x18001d768  mov     [rax], r8w
0x18001d76c  add     rax, 2
0x18001d770  dec     rcx
0x18001d773  sub     rdx, 1
0x18001d777  jnz     short loc_18001D755
0x18001d779  lea     rcx, [rax-2]
0x18001d77d  test    rdx, rdx
0x18001d780  cmovnz  rcx, rax
0x18001d784  mov     [rcx], r14w
0x18001d788  mov     rax, rdx
0x18001d78b  neg     rax
0x18001d78e  sbb     ecx, ecx
0x18001d790  not     ecx
0x18001d792  and     ecx, 8007007Ah
0x18001d798  mov     dword ptr [rsp+10E0h+var_10C0], ecx
0x18001d79c  test    rdx, rdx
0x18001d79f  jz      loc_18001DAC5
0x18001d7a5  lea     r8, [rsp+10E0h+Context]; Context
0x18001d7aa  lea     rdx, [rsp+10E0h+Delimiter]; Delimiter
0x18001d7af  lea     rcx, [rsp+10E0h+String]; String
0x18001d7b4  call    cs:__imp_wcstok_s
0x18001d7bb  nop     dword ptr [rax+rax+00h]
0x18001d7c0  mov     rbx, rax
0x18001d7c3  test    rax, rax
0x18001d7c6  jz      loc_18001D891
0x18001d7cc  lea     rdx, aHttp; "http:"
0x18001d7d3  mov     rcx, rax
0x18001d7d6  call    cs:__imp__o__wcsicmp
0x18001d7dd  nop     dword ptr [rax+rax+00h]
0x18001d7e2  mov     r14d, eax
0x18001d7e5  xor     edi, edi
0x18001d7e7  test    eax, eax
0x18001d7e9  setz    dil
0x18001d7ed  lea     rdx, aHttps_0; "https:"
0x18001d7f4  mov     rcx, rbx
0x18001d7f7  call    cs:__imp__o__wcsicmp
0x18001d7fe  nop     dword ptr [rax+rax+00h]
0x18001d803  mov     esi, eax
0x18001d805  test    r14d, r14d
0x18001d808  jz      short loc_18001D80E
0x18001d80a  test    eax, eax
0x18001d80c  jnz     short loc_18001D83A
0x18001d80e  lea     r8, [rsp+10E0h+Context]; Context
0x18001d813  lea     rdx, [rsp+10E0h+Delimiter]; Delimiter
0x18001d818  xor     ecx, ecx; String
0x18001d81a  call    cs:__imp_wcstok_s
0x18001d821  nop     dword ptr [rax+rax+00h]
0x18001d826  mov     rbx, rax
0x18001d829  neg     esi
0x18001d82b  sbb     eax, eax
0x18001d82d  and     eax, 0FFFFFE95h
0x18001d832  add     eax, 1BBh
0x18001d837  mov     [r15], eax
0x18001d83a  xor     esi, esi
0x18001d83c  mov     [rsp+10E0h+var_10B0], esi
0x18001d840  lea     rcx, [rsp+10E0h+var_10B0]
0x18001d845  call    cs:__imp_Mmpc_Lockdown_IsLockedToMmpc
0x18001d84c  nop     dword ptr [rax+rax+00h]
0x18001d851  mov     dword ptr [rsp+10E0h+var_10C0], eax
0x18001d855  cmp     eax, 8007007Fh
0x18001d85a  jnz     short loc_18001D862
0x18001d85c  mov     dword ptr [rsp+10E0h+var_10C0], esi
0x18001d860  jmp     short loc_18001D86A
0x18001d862  test    eax, eax
0x18001d864  js      loc_18001DAC5
0x18001d86a  test    r14d, r14d
0x18001d86d  jnz     short loc_18001D885
0x18001d86f  xor     r14d, r14d
0x18001d872  cmp     [rsp+10E0h+var_10B0], r14d
0x18001d877  jnz     short loc_18001D880
0x18001d879  cmp     [rsp+10E0h+var_10B8], r14d
0x18001d87e  jz      short loc_18001D888
0x18001d880  mov     edi, r14d
0x18001d883  jmp     short loc_18001D888
0x18001d885  xor     r14d, r14d
0x18001d888  xor     edi, 1
0x18001d88b  mov     cs:dword_1800706BC, edi
0x18001d891  mov     esi, 80070057h
0x18001d896  mov     edi, 7FFFFFFFh
0x18001d89b  test    rbx, rbx
0x18001d89e  jz      loc_18001D9BF
0x18001d8a4  mov     edx, 3Ah ; ':'; Ch
0x18001d8a9  mov     rcx, rbx; Str
0x18001d8ac  call    cs:__imp_wcschr
0x18001d8b3  nop     dword ptr [rax+rax+00h]
0x18001d8b8  test    rax, rax
0x18001d8bb  jz      short loc_18001D8DC
0x18001d8bd  mov     [rax], r14w
0x18001d8c1  lea     rcx, [rax+2]
0x18001d8c5  call    cs:__imp__o__wtoi
0x18001d8cc  nop     dword ptr [rax+rax+00h]
0x18001d8d1  mov     [r15], eax
0x18001d8d4  test    eax, eax
0x18001d8d6  jz      loc_18001DAC5
0x18001d8dc  mov     rdx, rdi
0x18001d8df  mov     rax, rbx
0x18001d8e2  cmp     [rax], r14w
0x18001d8e6  jz      short loc_18001D8F2
0x18001d8e8  add     rax, 2
0x18001d8ec  sub     rdx, 1
0x18001d8f0  jnz     short loc_18001D8E2
0x18001d8f2  mov     rax, rdx
0x18001d8f5  mov     rcx, rdi
0x18001d8f8  sub     rcx, rdx
0x18001d8fb  neg     rax
0x18001d8fe  sbb     r8, r8
0x18001d901  and     r8, rcx
0x18001d904  mov     rax, rdx
0x18001d907  neg     rax
0x18001d90a  sbb     ecx, ecx
0x18001d90c  not     ecx
0x18001d90e  and     ecx, esi
0x18001d910  mov     dword ptr [rsp+10E0h+var_10C0], ecx
0x18001d914  test    rdx, rdx
0x18001d917  jz      loc_18001DAC5
0x18001d91d  lea     r14, [r8+1]
0x18001d921  cmp     r14, r8
0x18001d924  jb      loc_18001DABD
0x18001d92a  xor     ecx, ecx
0x18001d92c  mov     [rsp+10E0h+var_10C0], rcx
0x18001d931  lea     eax, [rcx+2]
0x18001d934  mul     r14
0x18001d937  mov     r15, rax
0x18001d93a  test    rdx, rdx
0x18001d93d  jnz     loc_18001DABD
0x18001d943  mov     dword ptr [rsp+10E0h+var_10C0], ecx
0x18001d947  call    cs:__imp_GetProcessHeap
0x18001d94e  nop     dword ptr [rax+rax+00h]
0x18001d953  mov     rcx, rax; hHeap
0x18001d956  mov     r8, r15; dwBytes
0x18001d959  mov     edx, 8; dwFlags
0x18001d95e  call    cs:__imp_HeapAlloc
0x18001d965  nop     dword ptr [rax+rax+00h]
0x18001d96a  mov     [r13+0], rax
0x18001d96e  xor     r15d, r15d
0x18001d971  test    rax, rax
0x18001d974  jnz     short loc_18001D983
0x18001d976  mov     dword ptr [rsp+10E0h+var_10C0], 8007000Eh
0x18001d97e  jmp     loc_18001DAC5
0x18001d983  mov     dword ptr [rsp+10E0h+var_10C0], r15d
0x18001d988  mov     r8, rbx; unsigned __int16 *
0x18001d98b  mov     rdx, r14; unsigned __int64
0x18001d98e  mov     rcx, rax; unsigned __int16 *
0x18001d991  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d996  mov     dword ptr [rsp+10E0h+var_10C0], eax
0x18001d99a  test    eax, eax
0x18001d99c  js      loc_18001DAC5
0x18001d9a2  lea     r8, [rsp+10E0h+Context]; Context
0x18001d9a7  lea     rdx, [rsp+10E0h+var_10AC]; Delimiter
0x18001d9ac  xor     ecx, ecx; String
0x18001d9ae  call    cs:__imp_wcstok_s
0x18001d9b5  nop     dword ptr [rax+rax+00h]
0x18001d9ba  mov     rbx, rax
0x18001d9bd  jmp     short loc_18001D9C2
0x18001d9bf  xor     r15d, r15d
0x18001d9c2  mov     r14d, [rbp+0FE0h+arg_20]
0x18001d9c9  cmp     [rsp+10E0h+var_10B8], r15d
0x18001d9ce  cmovnz  r14d, r15d
0x18001d9d2  test    rbx, rbx
0x18001d9d5  jz      short loc_18001D9EF
0x18001d9d7  mov     r8, rdi
0x18001d9da  mov     rax, rbx
0x18001d9dd  cmp     [rax], r15w
0x18001d9e1  jz      short loc_18001DA12
0x18001d9e3  add     rax, 2
0x18001d9e7  sub     r8, 1
0x18001d9eb  jnz     short loc_18001D9DD
0x18001d9ed  jmp     short loc_18001DA12
0x18001d9ef  test    r14d, r14d
0x18001d9f2  jz      loc_18001DAC5
0x18001d9f8  mov     r8, rdi
0x18001d9fb  lea     rax, pwszObjectName; "EnrollmentServer/Discovery.svc"
0x18001da02  cmp     [rax], r15w
0x18001da06  jz      short loc_18001DA12
0x18001da08  add     rax, 2
0x18001da0c  sub     r8, 1
0x18001da10  jnz     short loc_18001DA02
0x18001da12  mov     rax, r8
0x18001da15  neg     rax
0x18001da18  sbb     edx, edx
0x18001da1a  not     edx
0x18001da1c  and     edx, esi
0x18001da1e  sub     rdi, r8
0x18001da21  mov     rax, r8
0x18001da24  neg     rax
0x18001da27  sbb     rcx, rcx
0x18001da2a  and     rcx, rdi
0x18001da2d  neg     r8
0x18001da30  sbb     rax, rax
0x18001da33  and     rax, rcx
0x18001da36  mov     dword ptr [rsp+10E0h+var_10C0], edx
0x18001da3a  test    edx, edx
0x18001da3c  js      loc_18001DAC5
0x18001da42  lea     rdi, [rax+1]
0x18001da46  cmp     rdi, rax
0x18001da49  jb      short loc_18001DABD
0x18001da4b  mov     [rsp+10E0h+var_10C0], r15
0x18001da50  mov     eax, 2
0x18001da55  mul     rdi
0x18001da58  mov     rsi, rax
0x18001da5b  test    rdx, rdx
0x18001da5e  jnz     short loc_18001DABD
0x18001da60  mov     dword ptr [rsp+10E0h+var_10C0], r15d
0x18001da65  test    r12, r12
0x18001da68  jz      short loc_18001DAC5
0x18001da6a  call    cs:__imp_GetProcessHeap
0x18001da71  nop     dword ptr [rax+rax+00h]
0x18001da76  mov     rcx, rax; hHeap
0x18001da79  mov     r8, rsi; dwBytes
0x18001da7c  mov     edx, 8; dwFlags
0x18001da81  call    cs:__imp_HeapAlloc
0x18001da88  nop     dword ptr [rax+rax+00h]
0x18001da8d  mov     [r12], rax
0x18001da91  mov     dword ptr [rsp+10E0h+var_10C0], r15d
0x18001da96  test    rbx, rbx
0x18001da99  jz      short loc_18001DAAF
0x18001da9b  mov     r8, rbx; unsigned __int16 *
0x18001da9e  mov     rdx, rdi; unsigned __int64
0x18001daa1  mov     rcx, rax; unsigned __int16 *
0x18001daa4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001daa9  mov     dword ptr [rsp+10E0h+var_10C0], eax
0x18001daad  jmp     short loc_18001DAC5
0x18001daaf  test    r14d, r14d
0x18001dab2  jz      short loc_18001DAC5
0x18001dab4  lea     r8, pwszObjectName; "EnrollmentServer/Discovery.svc"
0x18001dabb  jmp     short loc_18001DA9E
0x18001dabd  mov     dword ptr [rsp+10E0h+var_10C0], 80070216h
0x18001dac5  mov     ebx, dword ptr [rsp+10E0h+var_10C0]
0x18001dac9  lea     rcx, [rsp+10E0h+var_10A0]; this
0x18001dace  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001dad3  mov     eax, ebx
0x18001dad5  mov     rcx, [rbp+0FE0h+var_40]
0x18001dadc  xor     rcx, rsp; StackCookie
0x18001dadf  call    __security_check_cookie
0x18001dae4  mov     rbx, [rsp+10E0h+arg_0]
0x18001daec  add     rsp, 10B0h
0x18001daf3  pop     r15
0x18001daf5  pop     r14
0x18001daf7  pop     r13
0x18001daf9  pop     r12
0x18001dafb  pop     rdi
0x18001dafc  pop     rsi
0x18001dafd  pop     rbp
0x18001dafe  retn
  ... truncated ...
```
