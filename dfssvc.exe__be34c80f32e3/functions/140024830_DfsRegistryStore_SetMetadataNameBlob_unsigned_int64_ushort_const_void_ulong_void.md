# DfsRegistryStore::SetMetadataNameBlob(unsigned __int64,ushort const *,void *,ulong,void *)

- ea: `0x140024830`
- end: `0x1400249a5`
- name: `?SetMetadataNameBlob@DfsRegistryStore@@UEAAK_KPEBGPEAXK2@Z`
- size: `373`
- prototype: `unsigned int(DfsRegistryStore *__hidden this, unsigned __int64, const unsigned __int16 *, void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140005a94`
- `0x140005f20`
- `0x140024768`
- `0x140024830`
- `0x140057d14`
- `0x140057f64`
- `0x140057fc4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400248b4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400248b4`

## string_xrefs

- `0x1400248cf`: `ReparsePointSecurityDescriptor`
- `0x140024923`: `ReparsePointSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::SetMetadataNameBlob(
        DfsRegistryStore *this,
        HKEY a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned int a5,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DfsRegistryStore *v9; // rcx
  unsigned int v10; // ebx
  DWORD SecurityDescriptorLength; // eax
  unsigned int *v12; // rcx
  __int64 v14; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-10h]

  v14 = 0;
  v15 = 0;
  if ( !CRegistry::OpenKey((CRegistry *)&v14, a2, a3, 0x20006u) )
  {
    v10 = v15;
    goto LABEL_14;
  }
  v10 = DfsRegistryStore::SetMetadata(v9, a2, a3, L"ID", a4, a5);
  if ( v10 )
    goto LABEL_14;
  if ( !pSecurityDescriptor )
  {
    if ( !(unsigned int)CRegistry::DeleteValue((CRegistry *)&v14, 0, L"ReparsePointSecurityDescriptor") )
    {
      v10 = v15;
      if ( v15 == 2 )
        v10 = 0;
    }
    goto LABEL_14;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  if ( (unsigned int)CRegistry::SetValue(
                       (CRegistry *)&v14,
                       0,
                       L"ReparsePointSecurityDescriptor",
                       3u,
                       pSecurityDescriptor,
                       SecurityDescriptorLength) )
  {
LABEL_14:
    v12 = pWppControl;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_20;
  v12 = pWppControl;
  if ( pWppControl && (pWppControl[7] & 0x20) != 0 && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 32, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v15);
    goto LABEL_14;
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v12
    && (v12[7] & 0x20) != 0
    && *((_BYTE *)v12 + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)v12 + 2), 33, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v10);
  }
LABEL_20:
  CRegistry::~CRegistry((CRegistry *)&v14);
  return v10;
}

```

## disassembly

```asm
0x140024830  mov     rax, rsp
0x140024833  mov     [rax+8], rbx
0x140024837  mov     [rax+10h], rbp
0x14002483b  mov     [rax+18h], rsi
0x14002483f  mov     [rax+20h], rdi
0x140024843  push    r14
0x140024845  sub     rsp, 40h
0x140024849  mov     rsi, r9
0x14002484c  lea     rcx, [rax-18h]; this
0x140024850  xor     ebp, ebp
0x140024852  mov     r9d, 20006h; unsigned int
0x140024858  mov     [rax-18h], rbp
0x14002485c  mov     rbx, r8
0x14002485f  mov     [rax-10h], ebp
0x140024862  mov     rdi, rdx
0x140024865  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x14002486a  lea     r14, WPP_GLOBAL_Control
0x140024871  test    eax, eax
0x140024873  jnz     short loc_14002487E
0x140024875  mov     ebx, [rsp+48h+var_10]
0x140024879  jmp     loc_140024944
0x14002487e  mov     eax, [rsp+48h+arg_20]
0x140024882  lea     r9, aId; "ID"
0x140024889  mov     [rsp+48h+var_20], eax; unsigned int
0x14002488d  mov     r8, rbx; unsigned __int16 *
0x140024890  mov     rdx, rdi; HKEY
0x140024893  mov     [rsp+48h+var_28], rsi; void *
0x140024898  call    ?SetMetadata@DfsRegistryStore@@AEAAKPEAUHKEY__@@PEBG1PEAXK@Z; DfsRegistryStore::SetMetadata(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x14002489d  mov     ebx, eax
0x14002489f  test    eax, eax
0x1400248a1  jnz     loc_140024944
0x1400248a7  mov     rdi, [rsp+48h+pSecurityDescriptor]
0x1400248ac  test    rdi, rdi
0x1400248af  jz      short loc_140024923
0x1400248b1  mov     rcx, rdi; pSecurityDescriptor
0x1400248b4  call    cs:__imp_GetSecurityDescriptorLength
0x1400248bb  nop     dword ptr [rax+rax+00h]
0x1400248c0  mov     [rsp+48h+var_20], eax; DWORD
0x1400248c4  lea     r9d, [rbx+3]; unsigned int
0x1400248c8  xor     edx, edx; unsigned __int16 *
0x1400248ca  mov     [rsp+48h+var_28], rdi; LPCVOID
0x1400248cf  lea     r8, aReparsepointse; "ReparsePointSecurityDescriptor"
0x1400248d6  lea     rcx, [rsp+48h+var_18]; this
0x1400248db  call    ?SetValue@CRegistry@@AEAAHPEBG0KPEAXK@Z; CRegistry::SetValue(ushort const *,ushort const *,ulong,void *,ulong)
0x1400248e0  test    eax, eax
0x1400248e2  jnz     short loc_140024944
0x1400248e4  cmp     cs:WPP_GLOBAL_Control, r14
0x1400248eb  jz      loc_14002497D
0x1400248f1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400248f8  test    rcx, rcx
0x1400248fb  jz      short loc_14002494B
0x1400248fd  test    byte ptr [rcx+1Ch], 20h
0x140024901  jz      short loc_14002494B
0x140024903  cmp     byte ptr [rcx+19h], 2
0x140024907  jb      short loc_14002494B
0x140024909  mov     r9d, [rsp+48h+var_10]
0x14002490e  lea     edx, [rbx+20h]
0x140024911  mov     rcx, [rcx+10h]
0x140024915  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x14002491c  call    WPP_SF_D
0x140024921  jmp     short loc_140024944
0x140024923  lea     r8, aReparsepointse; "ReparsePointSecurityDescriptor"
0x14002492a  xor     edx, edx; unsigned __int16 *
0x14002492c  lea     rcx, [rsp+48h+var_18]; this
0x140024931  call    ?DeleteValue@CRegistry@@QEAAHPEBG0@Z; CRegistry::DeleteValue(ushort const *,ushort const *)
0x140024936  test    eax, eax
0x140024938  jnz     short loc_140024944
0x14002493a  mov     ebx, [rsp+48h+var_10]
0x14002493e  cmp     ebx, 2
0x140024941  cmovz   ebx, ebp
0x140024944  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002494b  cmp     cs:WPP_GLOBAL_Control, r14
0x140024952  jz      short loc_14002497D
0x140024954  test    rcx, rcx
0x140024957  jz      short loc_14002497D
0x140024959  test    byte ptr [rcx+1Ch], 20h
0x14002495d  jz      short loc_14002497D
0x14002495f  cmp     byte ptr [rcx+19h], 2
0x140024963  jb      short loc_14002497D
0x140024965  mov     rcx, [rcx+10h]
0x140024969  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140024970  mov     edx, 21h ; '!'
0x140024975  mov     r9d, ebx
0x140024978  call    WPP_SF_D
0x14002497d  lea     rcx, [rsp+48h+var_18]; this
0x140024982  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140024987  mov     rbp, [rsp+48h+arg_8]
0x14002498c  mov     eax, ebx
0x14002498e  mov     rbx, [rsp+48h+arg_0]
0x140024993  mov     rsi, [rsp+48h+arg_10]
0x140024998  mov     rdi, [rsp+48h+arg_18]
0x14002499d  add     rsp, 40h
0x1400249a1  pop     r14
0x1400249a3  retn
```
