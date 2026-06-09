# NtLmAllocateAndInitializeServiceSid(_UNICODE_STRING const *,void * *)

- ea: `0x180046b98`
- end: `0x180046c48`
- name: `?NtLmAllocateAndInitializeServiceSid@@YAJPEBU_UNICODE_STRING@@PEAPEAX@Z`
- size: `176`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18004a1c0`

## callees

- `0x180046b98`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x180046bc7`
- `ntdll!RtlCreateServiceSid` at `0x180046c33`
- `ntdll!RtlCreateServiceSid` at `0x180046bc7`
- `ntdll!RtlCreateServiceSid` at `0x180046c33`

## pseudocode

```c
__int64 __fastcall NtLmAllocateAndInitializeServiceSid(const struct _UNICODE_STRING *a1, void **a2)
{
  __int64 v2; // rdi
  NTSTATUS v3; // ebx
  void *v5; // rax
  ULONG ServiceSidLength; // [rsp+38h] [rbp+10h] BYREF
  int v7; // [rsp+3Ch] [rbp+14h]

  v7 = HIDWORD(a2);
  ServiceSidLength = 0;
  NtLmGlobalCscServiceSid = 0;
  if ( RtlCreateServiceSid((PUNICODE_STRING)&NtLmGlobalCscServiceName, 0, &ServiceSidLength) == -1073741789 )
  {
    v5 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(ServiceSidLength);
    v2 = (__int64)v5;
    if ( v5 )
    {
      v3 = RtlCreateServiceSid((PUNICODE_STRING)&NtLmGlobalCscServiceName, v5, &ServiceSidLength);
      if ( v3 >= 0 )
      {
        NtLmGlobalCscServiceSid = v2;
        return (unsigned int)v3;
      }
    }
    else
    {
      v3 = -1073741801;
    }
  }
  else
  {
    v2 = 0;
    v3 = -1073741823;
  }
  ((void (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180046b98  mov     rax, rsp
0x180046b9b  mov     [rax+8], rbx
0x180046b9f  mov     [rax+10h], rdx
0x180046ba3  push    rdi
0x180046ba4  sub     rsp, 20h
0x180046ba8  lea     r8, [rax+10h]; ServiceSidLength
0x180046bac  mov     dword ptr [rax+10h], 0
0x180046bb3  xor     edx, edx; ServiceSid
0x180046bb5  mov     cs:NtLmGlobalCscServiceSid, 0
0x180046bc0  lea     rcx, NtLmGlobalCscServiceName; ServiceName
0x180046bc7  call    cs:__imp_RtlCreateServiceSid
0x180046bcd  cmp     eax, 0C0000023h
0x180046bd2  jz      short loc_180046BFE
0x180046bd4  xor     edi, edi
0x180046bd6  mov     ebx, 0C0000001h
0x180046bdb  mov     rax, cs:LsaFunctions
0x180046be2  mov     rcx, rdi
0x180046be5  mov     rax, [rax+188h]
0x180046bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bf1  mov     eax, ebx
0x180046bf3  mov     rbx, [rsp+28h+arg_0]
0x180046bf8  add     rsp, 20h
0x180046bfc  pop     rdi
0x180046bfd  retn
0x180046bfe  mov     rax, cs:LsaFunctions
0x180046c05  mov     ecx, [rsp+28h+ServiceSidLength]
0x180046c09  mov     rax, [rax+180h]
0x180046c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c15  mov     rdi, rax
0x180046c18  test    rax, rax
0x180046c1b  jnz     short loc_180046C24
0x180046c1d  mov     ebx, 0C0000017h
0x180046c22  jmp     short loc_180046BDB
0x180046c24  lea     r8, [rsp+28h+ServiceSidLength]; ServiceSidLength
0x180046c29  mov     rdx, rdi; ServiceSid
0x180046c2c  lea     rcx, NtLmGlobalCscServiceName; ServiceName
0x180046c33  call    cs:__imp_RtlCreateServiceSid
0x180046c39  mov     ebx, eax
0x180046c3b  test    eax, eax
0x180046c3d  js      short loc_180046BDB
0x180046c3f  mov     cs:NtLmGlobalCscServiceSid, rdi
0x180046c46  jmp     short loc_180046BF1
```
