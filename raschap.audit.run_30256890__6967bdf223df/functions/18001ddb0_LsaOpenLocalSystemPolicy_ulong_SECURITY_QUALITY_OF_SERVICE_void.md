# LsaOpenLocalSystemPolicy(ulong,_SECURITY_QUALITY_OF_SERVICE *,void * *)

- ea: `0x18001ddb0`
- end: `0x18001de4b`
- name: `?LsaOpenLocalSystemPolicy@@YAKKPEAU_SECURITY_QUALITY_OF_SERVICE@@PEAPEAX@Z`
- size: `155`
- prototype: `unsigned int __fastcall(unsigned int, struct _SECURITY_QUALITY_OF_SERVICE *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001de54`

## callees

- `0x18001ddb0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001de35`
- `ntdll!RtlNtStatusToDosError` at `0x18001de35`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ddff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ddff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001de1c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001de1c`

## pseudocode

```c
ULONG __fastcall LsaOpenLocalSystemPolicy(__int64 a1, struct _SECURITY_QUALITY_OF_SERVICE *a2, void **a3)
{
  int v3; // ebx
  int v5; // eax
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp+18h] BYREF

  v3 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  PolicyHandle = 0;
  ObjectAttributes.SecurityQualityOfService = a2;
  while ( 1 )
  {
    v5 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
    if ( (unsigned int)(v5 + 1073610729) > 1 )
      break;
    if ( ++v3 >= 10 )
      break;
    Sleep(0xAu);
  }
  if ( v5 < 0 )
    return RtlNtStatusToDosError(v5);
  *a3 = PolicyHandle;
  return 0;
}

```

## disassembly

```asm
0x18001ddb0  mov     [rsp-8+arg_0], rbx
0x18001ddb5  mov     [rsp-8+arg_10], rdi
0x18001ddba  push    rbp
0x18001ddbb  mov     rbp, rsp
0x18001ddbe  sub     rsp, 50h
0x18001ddc2  xor     ebx, ebx
0x18001ddc4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001ddcc  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18001ddd0  mov     rdi, r8
0x18001ddd3  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x18001ddd7  mov     [rbp+ObjectAttributes.SecurityDescriptor], rbx
0x18001dddb  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18001dde3  mov     [rbp+PolicyHandle], 0
0x18001ddeb  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rdx
0x18001ddef  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18001ddf3  mov     r8d, 1; DesiredAccess
0x18001ddf9  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18001ddfd  xor     ecx, ecx; SystemName
0x18001ddff  call    cs:__imp_LsaOpenPolicy
0x18001de05  lea     ecx, [rax+3FFDFFE9h]
0x18001de0b  cmp     ecx, 1
0x18001de0e  ja      short loc_18001DE24
0x18001de10  inc     ebx
0x18001de12  cmp     ebx, 0Ah
0x18001de15  jge     short loc_18001DE24
0x18001de17  mov     ecx, 0Ah; dwMilliseconds
0x18001de1c  call    cs:__imp_Sleep
0x18001de22  jmp     short loc_18001DDEF
0x18001de24  test    eax, eax
0x18001de26  js      short loc_18001DE33
0x18001de28  mov     rax, [rbp+PolicyHandle]
0x18001de2c  mov     [rdi], rax
0x18001de2f  xor     eax, eax
0x18001de31  jmp     short loc_18001DE3B
0x18001de33  mov     ecx, eax; Status
0x18001de35  call    cs:__imp_RtlNtStatusToDosError
0x18001de3b  mov     rbx, [rsp+50h+arg_0]
0x18001de40  mov     rdi, [rsp+50h+arg_10]
0x18001de45  add     rsp, 50h
0x18001de49  pop     rbp
0x18001de4a  retn
```
