# LoadPolicyModule(ushort const *,ulong *,ushort *)

- ea: `0x18003061c`
- end: `0x1800306d6`
- name: `?LoadPolicyModule@@YAPEAUHINSTANCE__@@PEBGPEAKPEAG@Z`
- size: `186`
- prototype: `HINSTANCE __fastcall(LPCWSTR lpSrc, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800306dc`

## callees

- `0x180005665`
- `0x180022910`
- `0x18003061c`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18003066f`
- `KERNEL32!LoadLibraryW` at `0x18003066f`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003065e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003065e`
- `KERNEL32!GetLastError` at `0x180030683`
- `KERNEL32!GetLastError` at `0x180030683`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HINSTANCE __fastcall LoadPolicyModule(LPCWSTR lpSrc, unsigned int *a2, unsigned __int16 *a3)
{
  HMODULE LibraryW; // rbx
  DWORD LastError; // eax
  struct _EVENT_DESCRIPTOR v7; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x20Au);
  ExpandEnvironmentStringsW(lpSrc, Dst, 0x105u);
  LibraryW = LoadLibraryW(Dst);
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v7 = (struct _EVENT_DESCRIPTOR)TLS_E_LOADPOLICY;
    TLSLogEvent(&v7, 0xC800000B, lpSrc, LastError);
  }
  return LibraryW;
}

```

## disassembly

```asm
0x18003061c  mov     [rsp+arg_8], rbx
0x180030621  push    rdi
0x180030622  sub     rsp, 250h
0x180030629  mov     rax, cs:__security_cookie
0x180030630  xor     rax, rsp
0x180030633  mov     [rsp+258h+var_18], rax
0x18003063b  mov     rdi, rcx
0x18003063e  xor     edx, edx; Val
0x180030640  lea     rcx, [rsp+258h+Dst]; void *
0x180030645  mov     r8d, 20Ah; Size
0x18003064b  call    memset_0
0x180030650  mov     r8d, 105h; nSize
0x180030656  lea     rdx, [rsp+258h+Dst]; lpDst
0x18003065b  mov     rcx, rdi; lpSrc
0x18003065e  call    cs:__imp_ExpandEnvironmentStringsW
0x180030665  nop     dword ptr [rax+rax+00h]
0x18003066a  lea     rcx, [rsp+258h+Dst]; lpLibFileName
0x18003066f  call    cs:__imp_LoadLibraryW
0x180030676  nop     dword ptr [rax+rax+00h]
0x18003067b  mov     rbx, rax
0x18003067e  test    rax, rax
0x180030681  jnz     short loc_1800306B1
0x180030683  call    cs:__imp_GetLastError
0x18003068a  nop     dword ptr [rax+rax+00h]
0x18003068f  movups  xmm0, cs:TLS_E_LOADPOLICY
0x180030696  mov     r9d, eax
0x180030699  lea     rcx, [rsp+258h+var_238]; struct _EVENT_DESCRIPTOR
0x18003069e  mov     r8, rdi
0x1800306a1  mov     edx, 0C800000Bh; unsigned int
0x1800306a6  movdqu  xmmword ptr [rsp+258h+var_238.Id], xmm0
0x1800306ac  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x1800306b1  mov     rax, rbx
0x1800306b4  mov     rcx, [rsp+258h+var_18]
0x1800306bc  xor     rcx, rsp; StackCookie
0x1800306bf  call    __security_check_cookie
0x1800306c4  mov     rbx, [rsp+258h+arg_8]
0x1800306cc  add     rsp, 250h
0x1800306d3  pop     rdi
0x1800306d4  retn
```
