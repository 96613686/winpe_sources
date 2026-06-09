# SecGetProcessSecurityDescriptorDacl

- ea: `0x14000689c`
- end: `0x140006b4a`
- name: `SecGetProcessSecurityDescriptorDacl`
- size: `686`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a4f0`
- `0x14002c6b0`

## callees

- `0x14000689c`
- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x140011700`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x140006989`
- `ntoskrnl!RtlValidSid` at `0x140006989`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400068fb`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400068fb`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140006af8`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140006af8`
- `ntoskrnl!RtlGetAce` at `0x140006960`
- `ntoskrnl!RtlGetAce` at `0x140006a69`
- `ntoskrnl!RtlGetAce` at `0x140006960`
- `ntoskrnl!RtlGetAce` at `0x140006a69`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140006927`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140006927`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006a2b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006a2b`
- `ntoskrnl!RtlLengthSid` at `0x1400069a0`
- `ntoskrnl!RtlLengthSid` at `0x140006a94`
- `ntoskrnl!RtlLengthSid` at `0x140006ab4`
- `ntoskrnl!RtlLengthSid` at `0x1400069a0`
- `ntoskrnl!RtlLengthSid` at `0x140006a94`
- `ntoskrnl!RtlLengthSid` at `0x140006ab4`

## pseudocode

```c
NTSTATUS __fastcall SecGetProcessSecurityDescriptorDacl(void *a1, _OWORD *a2, ULONG *a3, unsigned int a4)
{
  _OWORD *v5; // rbx
  unsigned int v6; // r12d
  NTSTATUS result; // eax
  NTSTATUS DaclSecurityDescriptor; // edi
  PACL v9; // rsi
  ULONG v10; // r15d
  char *v11; // rax
  void *v12; // r12
  ULONG v13; // eax
  ULONG v14; // ecx
  ULONG v15; // edx
  unsigned int v16; // eax
  ULONG v17; // r15d
  int v18; // r13d
  SIZE_T v19; // rdx
  ULONG *PoolWithTag; // rax
  char *v21; // r12
  ULONG v22; // eax
  ULONG v23; // eax
  PVOID Ace; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+41h] [rbp-Fh] BYREF
  unsigned __int8 DaclPresent[6]; // [rsp+42h] [rbp-Eh] BYREF

  *a2 = 0;
  v5 = a2;
  a2[1] = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  v6 = a4;
  DaclPresent[0] = 0;
  DaclDefaulted = 0;
  Ace = 0;
  result = ObGetObjectSecurity(a1, &SecurityDescriptor, &MemoryAllocated);
  if ( result < 0 || !SecurityDescriptor )
    return result;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, (PACL *)v5, &DaclDefaulted);
  if ( DaclSecurityDescriptor >= 0 )
  {
    _mm_lfence();
    v9 = *(PACL *)v5;
    if ( *(_QWORD *)v5 )
    {
      v10 = 0;
      if ( v9->AceCount )
      {
        while ( 1 )
        {
          DaclSecurityDescriptor = RtlGetAce(v9, v10, &Ace);
          if ( DaclSecurityDescriptor < 0 )
            goto LABEL_33;
          v11 = (char *)Ace;
          if ( !*(_BYTE *)Ace )
          {
            ++*((_DWORD *)v5 + 2);
            v12 = v11 + 8;
            if ( !RtlValidSid(v11 + 8) )
              goto LABEL_33;
            v13 = RtlLengthSid(v12);
            v14 = *((_DWORD *)v5 + 3);
            v15 = v13 + v14 + 8;
            if ( v15 < v14 )
            {
              *((_DWORD *)v5 + 3) = -1;
              DaclSecurityDescriptor = -1073741675;
              goto LABEL_33;
            }
            *((_DWORD *)v5 + 3) = v15;
            DaclSecurityDescriptor = 0;
          }
          if ( ++v10 >= v9->AceCount )
          {
            v6 = a4;
            break;
          }
        }
      }
      v16 = *((_DWORD *)v5 + 3);
      v17 = 0;
      v18 = *((_DWORD *)v5 + 2);
      if ( v16 )
      {
        if ( !a3 || v6 < v16 )
        {
          v19 = *((unsigned int *)v5 + 3);
          if ( qword_140020008 )
            PoolWithTag = (ULONG *)qword_140020008(256, v19, 1701864275);
          else
            PoolWithTag = (ULONG *)ExAllocatePoolWithTag(PagedPool, v19, 0x65706353u);
          a3 = PoolWithTag;
          if ( !PoolWithTag )
          {
            DaclSecurityDescriptor = -1073741670;
            goto LABEL_33;
          }
          *((_BYTE *)v5 + 24) = 1;
        }
        *((_QWORD *)v5 + 2) = a3;
        if ( v9->AceCount )
        {
          do
          {
            DaclSecurityDescriptor = RtlGetAce(v9, v17, &Ace);
            if ( DaclSecurityDescriptor < 0 )
              break;
            if ( !*(_BYTE *)Ace )
            {
              v21 = (char *)Ace + 8;
              if ( --v18 )
                v22 = RtlLengthSid((char *)Ace + 8) + 8;
              else
                v22 = 0;
              *a3 = v22;
              a3[1] = *((_DWORD *)Ace + 1);
              v23 = RtlLengthSid(v21);
              memmove(a3 + 2, v21, v23);
              a3 = (ULONG *)((char *)a3 + *a3);
            }
            ++v17;
          }
          while ( v17 < v9->AceCount );
          v5 = a2;
        }
        goto LABEL_33;
      }
      *((_QWORD *)v5 + 2) = 1;
    }
  }
LABEL_33:
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
  if ( DaclSecurityDescriptor < 0 )
  {
    if ( *((_BYTE *)v5 + 24) )
    {
      _mm_lfence();
      SecFreePool(*((PVOID *)v5 + 2), 0x65706353u);
      *((_QWORD *)v5 + 2) = 0;
    }
  }
  return DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x14000689c  mov     [rsp-38h+arg_18], rbx
0x1400068a1  push    rbp
0x1400068a2  push    rsi
0x1400068a3  push    rdi
0x1400068a4  push    r12
0x1400068a6  push    r13
0x1400068a8  push    r14
0x1400068aa  push    r15
0x1400068ac  mov     rbp, rsp
0x1400068af  sub     rsp, 50h
0x1400068b3  mov     rax, cs:__security_cookie
0x1400068ba  xor     rax, rsp
0x1400068bd  mov     [rbp+var_8], rax
0x1400068c1  xor     r13d, r13d
0x1400068c4  mov     [rbp+var_28], rdx
0x1400068c8  xorps   xmm0, xmm0
0x1400068cb  mov     [rbp+var_30], r9d
0x1400068cf  movups  xmmword ptr [rdx], xmm0
0x1400068d2  mov     r14, r8
0x1400068d5  mov     rbx, rdx
0x1400068d8  movups  xmmword ptr [rdx+10h], xmm0
0x1400068dc  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400068e0  mov     [rbp+SecurityDescriptor], r13
0x1400068e4  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x1400068e8  mov     [rbp+MemoryAllocated], r13b
0x1400068ec  mov     r12d, r9d
0x1400068ef  mov     [rbp+DaclPresent], r13b
0x1400068f3  mov     [rbp+DaclDefaulted], r13b
0x1400068f7  mov     [rbp+Ace], r13
0x1400068fb  call    cs:__imp_ObGetObjectSecurity
0x140006902  nop     dword ptr [rax+rax+00h]
0x140006907  test    eax, eax
0x140006909  js      loc_140006B25
0x14000690f  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140006913  test    rcx, rcx
0x140006916  jz      loc_140006B25
0x14000691c  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x140006920  mov     r8, rbx; Dacl
0x140006923  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x140006927  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000692e  nop     dword ptr [rax+rax+00h]
0x140006933  mov     edi, eax
0x140006935  test    eax, eax
0x140006937  js      loc_140006AEC
0x14000693d  lfence
0x140006940  mov     rsi, [rbx]
0x140006943  test    rsi, rsi
0x140006946  jz      loc_140006AEC
0x14000694c  mov     r15d, r13d
0x14000694f  cmp     r13w, [rsi+4]
0x140006954  jnb     short loc_1400069CE
0x140006956  lea     r8, [rbp+Ace]; Ace
0x14000695a  mov     edx, r15d; AceIndex
0x14000695d  mov     rcx, rsi; Acl
0x140006960  call    cs:__imp_RtlGetAce
0x140006967  nop     dword ptr [rax+rax+00h]
0x14000696c  mov     edi, eax
0x14000696e  test    eax, eax
0x140006970  js      loc_140006AEC
0x140006976  mov     rax, [rbp+Ace]
0x14000697a  cmp     [rax], r13b
0x14000697d  jnz     short loc_1400069BE
0x14000697f  inc     dword ptr [rbx+8]
0x140006982  lea     r12, [rax+8]
0x140006986  mov     rcx, r12; Sid
0x140006989  call    cs:__imp_RtlValidSid
0x140006990  nop     dword ptr [rax+rax+00h]
0x140006995  test    al, al
0x140006997  jz      loc_140006AEC
0x14000699d  mov     rcx, r12; Sid
0x1400069a0  call    cs:__imp_RtlLengthSid
0x1400069a7  nop     dword ptr [rax+rax+00h]
0x1400069ac  mov     ecx, [rbx+0Ch]
0x1400069af  lea     edx, [rcx+8]
0x1400069b2  add     edx, eax
0x1400069b4  cmp     edx, ecx
0x1400069b6  jb      short loc_1400069E9
0x1400069b8  mov     [rbx+0Ch], edx
0x1400069bb  mov     edi, r13d
0x1400069be  movzx   eax, word ptr [rsi+4]
0x1400069c2  inc     r15d
0x1400069c5  cmp     r15d, eax
0x1400069c8  jb      short loc_140006956
0x1400069ca  mov     r12d, [rbp+var_30]
0x1400069ce  mov     eax, [rbx+0Ch]
0x1400069d1  xor     r15d, r15d
0x1400069d4  mov     r13d, [rbx+8]
0x1400069d8  test    eax, eax
0x1400069da  jnz     short loc_1400069FA
0x1400069dc  mov     qword ptr [rbx+10h], 1
0x1400069e4  jmp     loc_140006AE9
0x1400069e9  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1400069f0  mov     edi, 0C0000095h
0x1400069f5  jmp     loc_140006AEC
0x1400069fa  test    r14, r14
0x1400069fd  jz      short loc_140006A04
0x1400069ff  cmp     r12d, eax
0x140006a02  jnb     short loc_140006A4D
0x140006a04  mov     rdx, rax; NumberOfBytes
0x140006a07  mov     r8d, 65706353h; Tag
0x140006a0d  mov     rax, cs:qword_140020008
0x140006a14  test    rax, rax
0x140006a17  jz      short loc_140006A26
0x140006a19  mov     ecx, 100h
0x140006a1e  call    cs:__guard_dispatch_icall_fptr
0x140006a24  jmp     short loc_140006A37
0x140006a26  mov     ecx, 1; PoolType
0x140006a2b  call    cs:__imp_ExAllocatePoolWithTag
0x140006a32  nop     dword ptr [rax+rax+00h]
0x140006a37  mov     r14, rax
0x140006a3a  test    rax, rax
0x140006a3d  jnz     short loc_140006A49
0x140006a3f  mov     edi, 0C000009Ah
0x140006a44  jmp     loc_140006AE9
0x140006a49  mov     byte ptr [rbx+18h], 1
0x140006a4d  xor     eax, eax
0x140006a4f  mov     [rbx+10h], r14
0x140006a53  cmp     ax, [rsi+4]
0x140006a57  jnb     loc_140006AE9
0x140006a5d  xor     ebx, ebx
0x140006a5f  lea     r8, [rbp+Ace]; Ace
0x140006a63  mov     edx, r15d; AceIndex
0x140006a66  mov     rcx, rsi; Acl
0x140006a69  call    cs:__imp_RtlGetAce
0x140006a70  nop     dword ptr [rax+rax+00h]
0x140006a75  mov     edi, eax
0x140006a77  test    eax, eax
0x140006a79  js      short loc_140006AE5
0x140006a7b  mov     rax, [rbp+Ace]
0x140006a7f  cmp     [rax], bl
0x140006a81  jnz     short loc_140006AD5
0x140006a83  lea     r12, [rax+8]
0x140006a87  add     r13d, 0FFFFFFFFh
0x140006a8b  jnz     short loc_140006A91
0x140006a8d  mov     eax, ebx
0x140006a8f  jmp     short loc_140006AA3
0x140006a91  mov     rcx, r12; Sid
0x140006a94  call    cs:__imp_RtlLengthSid
0x140006a9b  nop     dword ptr [rax+rax+00h]
0x140006aa0  add     eax, 8
0x140006aa3  mov     [r14], eax
0x140006aa6  mov     rax, [rbp+Ace]
0x140006aaa  mov     ecx, [rax+4]
0x140006aad  mov     [r14+4], ecx
0x140006ab1  mov     rcx, r12; Sid
0x140006ab4  call    cs:__imp_RtlLengthSid
0x140006abb  nop     dword ptr [rax+rax+00h]
0x140006ac0  mov     r8d, eax; Size
0x140006ac3  lea     rcx, [r14+8]; void *
0x140006ac7  mov     rdx, r12; Src
0x140006aca  call    memmove
0x140006acf  mov     eax, [r14]
0x140006ad2  add     r14, rax
0x140006ad5  movzx   eax, word ptr [rsi+4]
0x140006ad9  inc     r15d
0x140006adc  cmp     r15d, eax
0x140006adf  jb      loc_140006A5F
0x140006ae5  mov     rbx, [rbp+var_28]
0x140006ae9  xor     r13d, r13d
0x140006aec  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140006af0  test    rcx, rcx
0x140006af3  jz      short loc_140006B04
0x140006af5  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x140006af8  call    cs:__imp_ObReleaseObjectSecurity
0x140006aff  nop     dword ptr [rax+rax+00h]
0x140006b04  test    edi, edi
0x140006b06  jns     short loc_140006B23
0x140006b08  cmp     [rbx+18h], r13b
0x140006b0c  jz      short loc_140006B23
0x140006b0e  lfence
0x140006b11  mov     rcx, [rbx+10h]; P
0x140006b15  mov     edx, 65706353h; Tag
0x140006b1a  call    SecFreePool
0x140006b1f  mov     [rbx+10h], r13
0x140006b23  mov     eax, edi
0x140006b25  mov     rcx, [rbp+var_8]
0x140006b29  xor     rcx, rsp; StackCookie
0x140006b2c  call    __security_check_cookie
0x140006b31  mov     rbx, [rsp+50h+arg_18]
0x140006b39  add     rsp, 50h
0x140006b3d  pop     r15
0x140006b3f  pop     r14
0x140006b41  pop     r13
0x140006b43  pop     r12
0x140006b45  pop     rdi
0x140006b46  pop     rsi
0x140006b47  pop     rbp
0x140006b48  retn
```
