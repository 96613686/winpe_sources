# FltQueryQuotaInformationFile

- ea: `0x180053460`
- end: `0x180053648`
- name: `FltQueryQuotaInformationFile`
- size: `488`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int, char, __int64, int, PSID Sid, char, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180087370`

## callees

- `0x180008000`
- `0x180008080`
- `0x180008a70`
- `0x180009f20`
- `0x180053460`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x1800534d5`
- `ntoskrnl!RtlValidSid` at `0x180053560`
- `ntoskrnl!RtlValidSid` at `0x1800534d5`
- `ntoskrnl!RtlValidSid` at `0x180053560`
- `ntoskrnl!RtlLengthSid` at `0x1800534e9`
- `ntoskrnl!RtlLengthSid` at `0x1800534e9`

## pseudocode

```c
NTSTATUS __fastcall FltQueryQuotaInformationFile(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        void *a4,
        ULONG a5,
        char a6,
        __int64 a7,
        int a8,
        PSID Sid,
        char a10,
        _DWORD *a11)
{
  void *v11; // rsi
  struct _FLT_INSTANCE *v14; // rbx
  __int64 v15; // rdi
  int v16; // esi
  unsigned int *i; // r14
  signed int v18; // ecx
  __int64 v19; // rax
  __int64 v20; // rsi
  unsigned int v21; // ebx
  NTSTATUS result; // eax
  PFLT_CALLBACK_DATA v23; // rbx
  int Status; // edi
  PFLT_CALLBACK_DATA RetNewCallbackData; // [rsp+20h] [rbp-38h] BYREF

  v11 = a4;
  v14 = Instance;
  RetNewCallbackData = 0;
  v15 = 0;
  if ( a7 && a8 )
    v15 = a7;
  if ( v15 )
  {
    v16 = a8;
    for ( i = (unsigned int *)v15; v16 >= 20 && RtlValidSid(i + 2); i = (unsigned int *)((char *)i + v19) )
    {
      v18 = RtlLengthSid(i + 2) + 8;
      v19 = *i;
      if ( !(_DWORD)v19 )
      {
        if ( v16 - v18 >= 0 )
        {
          v20 = 0;
          v21 = 0;
          goto LABEL_16;
        }
        break;
      }
      if ( v18 > (int)v19 )
        break;
      if ( (v19 & 3) != 0 )
        break;
      v16 -= v19;
      if ( v16 < 0 )
        break;
    }
    v20 = (unsigned int)((_DWORD)i - v15);
    v21 = -1073741210;
LABEL_16:
    if ( (int)FltpDbgStatus(v21, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 7221, 0) < 0 )
    {
      *(_QWORD *)(a3 + 8) = v20;
      return v21;
    }
    v14 = Instance;
    v11 = a4;
  }
  if ( Sid && !RtlValidSid(Sid) )
    return -1073741704;
  result = FltAllocateCallbackData(v14, FileObject, &RetNewCallbackData);
  if ( result >= 0 )
  {
    v23 = RetNewCallbackData;
    RetNewCallbackData->Iopb->MajorFunction = 25;
    v23->Iopb->Parameters.Read.ByteOffset.QuadPart = v15;
    v23->Iopb->Parameters.Create.EaLength = a8;
    v23->Iopb->Parameters.Read.Length = a5;
    v23->Iopb->Parameters.QueryEa.EaList = Sid;
    v23->Iopb->Parameters.Create.EaBuffer = v11;
    if ( a10 )
      v23->Iopb->OperationFlags |= 1u;
    if ( a6 )
      v23->Iopb->OperationFlags |= 2u;
    if ( Sid )
      v23->Iopb->OperationFlags |= 4u;
    FltPerformSynchronousIo(v23);
    Status = v23->IoStatus.Status;
    if ( a11 )
    {
      if ( Status >= 0 )
        *a11 = v23->IoStatus.Information;
    }
    FltFreeCallbackData(v23);
    return Status;
  }
  return result;
}

```

## disassembly

```asm
0x180053460  mov     rax, rsp
0x180053463  mov     [rax+10h], rbx
0x180053467  mov     [rax+18h], rsi
0x18005346b  mov     [rax+20h], r9
0x18005346f  mov     [rax+8], rcx
0x180053473  push    rdi
0x180053474  push    r12
0x180053476  push    r13
0x180053478  push    r14
0x18005347a  push    r15
0x18005347c  sub     rsp, 30h
0x180053480  mov     rsi, r9
0x180053483  mov     r13, r8
0x180053486  mov     r12, rdx
0x180053489  mov     rbx, rcx
0x18005348c  mov     qword ptr [rax-38h], 0
0x180053494  xor     edi, edi
0x180053496  mov     rax, [rsp+58h+arg_30]
0x18005349e  test    rax, rax
0x1800534a1  jz      short loc_1800534AE
0x1800534a3  cmp     [rsp+58h+arg_38], edi
0x1800534aa  cmovnz  rdi, rax
0x1800534ae  mov     r15, [rsp+58h+Sid]
0x1800534b6  test    rdi, rdi
0x1800534b9  jz      loc_180053558
0x1800534bf  mov     esi, [rsp+58h+arg_38]
0x1800534c6  mov     r14, rdi
0x1800534c9  mov     rbx, r14
0x1800534cc  cmp     esi, 14h
0x1800534cf  jl      short loc_18005351A
0x1800534d1  lea     rcx, [r14+8]; Sid
0x1800534d5  call    cs:__imp_RtlValidSid
0x1800534dc  nop     dword ptr [rax+rax+00h]
0x1800534e1  test    al, al
0x1800534e3  jz      short loc_18005351A
0x1800534e5  lea     rcx, [r14+8]; Sid
0x1800534e9  call    cs:__imp_RtlLengthSid
0x1800534f0  nop     dword ptr [rax+rax+00h]
0x1800534f5  lea     ecx, [rax+8]
0x1800534f8  mov     eax, [r14]
0x1800534fb  test    eax, eax
0x1800534fd  jz      short loc_180053510
0x1800534ff  cmp     ecx, eax
0x180053501  jg      short loc_18005351A
0x180053503  test    al, 3
0x180053505  jnz     short loc_18005351A
0x180053507  sub     esi, eax
0x180053509  js      short loc_18005351A
0x18005350b  add     r14, rax
0x18005350e  jmp     short loc_1800534C9
0x180053510  cmp     esi, ecx
0x180053512  js      short loc_18005351A
0x180053514  xor     esi, esi
0x180053516  xor     ebx, ebx
0x180053518  jmp     short loc_180053524
0x18005351a  sub     rbx, rdi
0x18005351d  mov     esi, ebx
0x18005351f  mov     ebx, 0C0000266h
0x180053524  mov     r8d, 1C35h
0x18005352a  xor     r9d, r9d
0x18005352d  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180053534  mov     ecx, ebx
0x180053536  call    FltpDbgStatus
0x18005353b  test    eax, eax
0x18005353d  jns     short loc_18005354E
0x18005353f  mov     [r13+8], rsi
0x180053543  jmp     short loc_180053547
0x180053545  mov     ebx, eax
0x180053547  mov     eax, ebx
0x180053549  jmp     loc_18005362F
0x18005354e  mov     rbx, [rsp+58h+arg_0]
0x180053553  mov     rsi, [rsp+58h+arg_18]
0x180053558  test    r15, r15
0x18005355b  jz      short loc_18005357A
0x18005355d  mov     rcx, r15; Sid
0x180053560  call    cs:__imp_RtlValidSid
0x180053567  nop     dword ptr [rax+rax+00h]
0x18005356c  test    al, al
0x18005356e  jnz     short loc_18005357A
0x180053570  mov     eax, 0C0000078h
0x180053575  jmp     loc_18005362F
0x18005357a  lea     r8, [rsp+58h+RetNewCallbackData]; RetNewCallbackData
0x18005357f  mov     rdx, r12; FileObject
0x180053582  mov     rcx, rbx; Instance
0x180053585  call    FltAllocateCallbackData
0x18005358a  test    eax, eax
0x18005358c  js      loc_18005362F
0x180053592  mov     rbx, [rsp+58h+RetNewCallbackData]
0x180053597  mov     rax, [rbx+10h]
0x18005359b  mov     byte ptr [rax+4], 19h
0x18005359f  mov     rax, [rbx+10h]
0x1800535a3  mov     [rax+28h], rdi
0x1800535a7  mov     rcx, [rbx+10h]
0x1800535ab  mov     eax, [rsp+58h+arg_38]
0x1800535b2  mov     [rcx+30h], eax
0x1800535b5  mov     rcx, [rbx+10h]
0x1800535b9  mov     eax, [rsp+58h+arg_20]
0x1800535c0  mov     [rcx+18h], eax
0x1800535c3  mov     rax, [rbx+10h]
0x1800535c7  mov     [rax+20h], r15
0x1800535cb  mov     rax, [rbx+10h]
0x1800535cf  mov     [rax+38h], rsi
0x1800535d3  cmp     [rsp+58h+arg_48], 0
0x1800535db  jz      short loc_1800535E5
0x1800535dd  mov     rax, [rbx+10h]
0x1800535e1  or      byte ptr [rax+6], 1
0x1800535e5  cmp     [rsp+58h+arg_28], 0
0x1800535ed  jz      short loc_1800535F7
0x1800535ef  mov     rax, [rbx+10h]
0x1800535f3  or      byte ptr [rax+6], 2
0x1800535f7  test    r15, r15
0x1800535fa  jz      short loc_180053604
0x1800535fc  mov     rax, [rbx+10h]
0x180053600  or      byte ptr [rax+6], 4
0x180053604  mov     rcx, rbx; CallbackData
0x180053607  call    FltPerformSynchronousIo
0x18005360c  mov     edi, [rbx+18h]
0x18005360f  mov     rax, [rsp+58h+arg_50]
0x180053617  test    rax, rax
0x18005361a  jz      short loc_180053625
0x18005361c  test    edi, edi
0x18005361e  js      short loc_180053625
0x180053620  mov     edx, [rbx+20h]
0x180053623  mov     [rax], edx
0x180053625  mov     rcx, rbx; CallbackData
0x180053628  call    FltFreeCallbackData
0x18005362d  mov     eax, edi
0x18005362f  mov     rbx, [rsp+58h+arg_8]
0x180053634  mov     rsi, [rsp+58h+arg_10]
0x180053639  add     rsp, 30h
0x18005363d  pop     r15
0x18005363f  pop     r14
0x180053641  pop     r13
0x180053643  pop     r12
0x180053645  pop     rdi
0x180053646  retn
```
