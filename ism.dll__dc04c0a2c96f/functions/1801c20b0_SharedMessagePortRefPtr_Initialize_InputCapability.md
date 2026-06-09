# SharedMessagePortRefPtr::Initialize(InputCapability)

- ea: `0x1801c20b0`
- end: `0x1801c226e`
- name: `?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c1990`

## callees

- `0x18019e348`
- `0x18019fc60`
- `0x1801c20b0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801c214f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801c214f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c2252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c2252`
- `CoreUIComponents!CoreUIClientCreate` at `0x1801c20d8`
- `CoreUIComponents!CoreUIClientCreate` at `0x1801c20d8`

## pseudocode

```c
__int64 __fastcall SharedMessagePortRefPtr::Initialize(_QWORD *a1)
{
  PSECURITY_DESCRIPTOR v2; // r14
  int v3; // eax
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // ebx
  int v7; // r9d
  __int64 (__fastcall *v8)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *); // r11
  const wchar_t *v9; // rax
  const wchar_t *v10; // rdx
  int v11; // ecx
  __int64 v12; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+78h] [rbp+28h]
  __int64 v18; // [rsp+90h] [rbp+40h] BYREF
  __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v19 = 0;
  v18 = 0;
  v2 = 0;
  v3 = CoreUIClientCreate(&v19);
  v6 = v3;
  if ( v3 < 0 )
  {
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) == 0 )
      goto LABEL_24;
    v7 = 116;
    goto LABEL_4;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, &v18);
  v6 = v3;
  if ( v3 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-419202837"
             "2-3968301570-1997628692-1435953622)",
            1u,
            &SecurityDescriptor,
            0) )
      FailFastWithHR(-2147467259, retaddr, 0xF3u);
    v2 = SecurityDescriptor;
    SecurityDescriptor = 0;
    v8 = *(__int64 (__fastcall **)(__int64, unsigned __int64, PSECURITY_DESCRIPTOR, _QWORD *))(*(_QWORD *)v18 + 24LL);
    v9 = L"Input\\Core.AlpcPort\\Server";
    if ( L"Input\\Core.AlpcPort\\Server" )
    {
      v10 = L"Input\\Core.AlpcPort\\Server";
      v16 = L"Input\\Core.AlpcPort\\Server";
      v11 = 0;
      while ( *v9 )
      {
        ++v9;
        ++v11;
      }
      v15 = v11 | 0x80000000;
    }
    else
    {
      v10 = 0;
      v16 = 0;
    }
    v3 = v8(v18, (unsigned __int64)&v15 & -(__int64)(v10 != 0), v2, a1 + 1);
    v6 = v3;
    if ( v3 >= 0 )
    {
      v12 = v18;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      if ( *a1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
      *a1 = v12;
    }
    else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    {
      v7 = 127;
      goto LABEL_4;
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v7 = 119;
LABEL_4:
    McTemplateU0sqq_EventWriteTransfer(v5, v4, (unsigned int)"SharedMessagePortRefPtr::Initialize", v7, v3);
  }
LABEL_24:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  LocalFree(v2);
  return v6;
}

```

## disassembly

```asm
0x1801c20b0  mov     [rsp-28h+arg_0], rbx
0x1801c20b5  push    rbp
0x1801c20b6  push    rsi
0x1801c20b7  push    rdi
0x1801c20b8  push    r14
0x1801c20ba  push    r15
0x1801c20bc  mov     rbp, rsp
0x1801c20bf  sub     rsp, 50h
0x1801c20c3  xor     r15d, r15d
0x1801c20c6  mov     rsi, rcx
0x1801c20c9  lea     rcx, [rbp+arg_18]
0x1801c20cd  mov     [rbp+arg_18], r15
0x1801c20d1  mov     [rbp+arg_10], r15
0x1801c20d5  mov     r14d, r15d
0x1801c20d8  call    cs:__imp_CoreUIClientCreate
0x1801c20de  mov     ebx, eax
0x1801c20e0  test    eax, eax
0x1801c20e2  jns     short loc_1801C210A
0x1801c20e4  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c20eb  jz      loc_1801C221D
0x1801c20f1  lea     r9d, [r15+74h]
0x1801c20f5  lea     r8, aSharedmessagep; "SharedMessagePortRefPtr::Initialize"
0x1801c20fc  mov     [rsp+50h+var_30], eax
0x1801c2100  call    McTemplateU0sqq_EventWriteTransfer
0x1801c2105  jmp     loc_1801C221D
0x1801c210a  mov     rcx, [rbp+arg_18]
0x1801c210e  lea     rdx, [rbp+arg_10]
0x1801c2112  mov     rax, [rcx]
0x1801c2115  mov     rax, [rax+30h]
0x1801c2119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c211e  mov     ebx, eax
0x1801c2120  test    eax, eax
0x1801c2122  jns     short loc_1801C2139
0x1801c2124  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c212b  jz      loc_1801C221D
0x1801c2131  mov     r9d, 77h ; 'w'
0x1801c2137  jmp     short loc_1801C20F5
0x1801c2139  xor     r9d, r9d; SecurityDescriptorSize
0x1801c213c  mov     [rbp+SecurityDescriptor], r15
0x1801c2140  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801c2144  lea     rcx, aDA0x01WdA0x01A; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x1801c214b  lea     edx, [r9+1]; StringSDRevision
0x1801c214f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801c2155  test    eax, eax
0x1801c2157  jnz     short loc_1801C216D
0x1801c2159  mov     rdx, [rbp+28h]; unsigned __int64
0x1801c215d  mov     ecx, 80004005h; int
0x1801c2162  mov     r8d, 0F3h; unsigned __int64
0x1801c2168  call    ?FailFastWithHR@@YAXJ_K0@Z; FailFastWithHR(long,unsigned __int64,unsigned __int64)
0x1801c216d  mov     r10, [rbp+arg_10]
0x1801c2171  mov     r14, [rbp+SecurityDescriptor]
0x1801c2175  mov     [rbp+SecurityDescriptor], r15
0x1801c2179  mov     rax, [r10]
0x1801c217c  mov     r11, [rax+18h]
0x1801c2180  mov     rax, cs:off_1801D5FC0; "Input\\Core.AlpcPort\\Server"
0x1801c2187  test    rax, rax
0x1801c218a  jz      short loc_1801C21AE
0x1801c218c  mov     rdx, rax
0x1801c218f  mov     [rbp+var_10], rax
0x1801c2193  mov     rcx, r15
0x1801c2196  jmp     short loc_1801C219F
0x1801c2198  lea     rax, [rax+2]
0x1801c219c  inc     rcx
0x1801c219f  cmp     [rax], r15w
0x1801c21a3  jnz     short loc_1801C2198
0x1801c21a5  bts     ecx, 1Fh
0x1801c21a9  mov     [rbp+var_18], ecx
0x1801c21ac  jmp     short loc_1801C21B5
0x1801c21ae  mov     rdx, r15
0x1801c21b1  mov     [rbp+var_10], rdx
0x1801c21b5  neg     rdx
0x1801c21b8  lea     rax, [rbp+var_18]
0x1801c21bc  lea     r9, [rsi+8]
0x1801c21c0  mov     r8, r14
0x1801c21c3  sbb     rdx, rdx
0x1801c21c6  mov     rcx, r10
0x1801c21c9  and     rdx, rax
0x1801c21cc  mov     rax, r11
0x1801c21cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c21d4  mov     ebx, eax
0x1801c21d6  test    eax, eax
0x1801c21d8  jns     short loc_1801C21EE
0x1801c21da  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1801c21e1  jz      short loc_1801C221D
0x1801c21e3  mov     r9d, 7Fh
0x1801c21e9  jmp     loc_1801C20F5
0x1801c21ee  mov     rdi, [rbp+arg_10]
0x1801c21f2  test    rdi, rdi
0x1801c21f5  jz      short loc_1801C2206
0x1801c21f7  mov     rax, [rdi]
0x1801c21fa  mov     rcx, rdi
0x1801c21fd  mov     rax, [rax+8]
0x1801c2201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c2206  mov     rcx, [rsi]
0x1801c2209  test    rcx, rcx
0x1801c220c  jz      short loc_1801C221A
0x1801c220e  mov     rax, [rcx]
0x1801c2211  mov     rax, [rax+10h]
0x1801c2215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c221a  mov     [rsi], rdi
0x1801c221d  mov     rcx, [rbp+arg_18]
0x1801c2221  test    rcx, rcx
0x1801c2224  jz      short loc_1801C2236
0x1801c2226  mov     rax, [rcx]
0x1801c2229  mov     rax, [rax+10h]
0x1801c222d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c2232  mov     [rbp+arg_18], r15
0x1801c2236  mov     rcx, [rbp+arg_10]
0x1801c223a  test    rcx, rcx
0x1801c223d  jz      short loc_1801C224F
0x1801c223f  mov     rax, [rcx]
0x1801c2242  mov     rax, [rax+10h]
0x1801c2246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c224b  mov     [rbp+arg_10], r15
0x1801c224f  mov     rcx, r14; hMem
0x1801c2252  call    cs:__imp_LocalFree
0x1801c2258  mov     eax, ebx
0x1801c225a  mov     rbx, [rsp+50h+arg_0]
0x1801c2262  add     rsp, 50h
0x1801c2266  pop     r15
0x1801c2268  pop     r14
0x1801c226a  pop     rdi
0x1801c226b  pop     rsi
0x1801c226c  pop     rbp
0x1801c226d  retn
```
