# LsapGetPrivilegeDisplayName(ulong,ulong,ushort,ushort,_UNICODE_STRING * *,ushort *)

- ea: `0x1801086d0`
- end: `0x1801089b6`
- name: `?LsapGetPrivilegeDisplayName@@YAJKKGGPEAPEAU_UNICODE_STRING@@PEAG@Z`
- size: `742`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned __int16, struct _UNICODE_STRING **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18008d8a8`

## callees

- `0x1800b86d0`
- `0x1800b8ac0`
- `0x1800b9420`
- `0x1800bd6e0`
- `0x1801086d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108987`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180108784`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801088cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801088f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180108784`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801088cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801088f5`
- `ntdll!RtlFindMessage` at `0x18010886f`
- `ntdll!RtlFindMessage` at `0x18010886f`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18010874d`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1801087b5`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18010874d`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1801087b5`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x180108829`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x180108971`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x180108829`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x180108971`

## pseudocode

```c
__int64 __fastcall LsapGetPrivilegeDisplayName(
        unsigned int a1,
        int a2,
        __int16 a3,
        __int16 a4,
        struct _UNICODE_STRING **a5,
        unsigned __int16 *a6)
{
  unsigned int v6; // edi
  __int16 v7; // r14
  __int64 v8; // r15
  unsigned int ThreadPreferredUILanguages; // eax
  unsigned int v10; // ebx
  wchar_t *v11; // rsi
  char v12; // r12
  wchar_t *v13; // rax
  __int64 v14; // rbx
  unsigned __int16 v15; // r13
  int v16; // eax
  unsigned __int64 v17; // rcx
  PMESSAGE_RESOURCE_ENTRY v18; // r14
  __int64 v19; // rdi
  __int64 v20; // r15
  struct _UNICODE_STRING *v21; // rax
  struct _UNICODE_STRING *v22; // rbx
  USHORT v23; // di
  WCHAR *v24; // rax
  unsigned __int16 *v25; // rax
  wchar_t *v26; // rdx
  __int64 v27; // rcx
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  _WORD v31[4]; // [rsp+38h] [rbp-C8h]
  int v32; // [rsp+40h] [rbp-C0h]
  PMESSAGE_RESOURCE_ENTRY MessageResourceEntry; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v34; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING **v35; // [rsp+58h] [rbp-A8h]
  wchar_t Buffer[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[112]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = 0;
  v35 = a5;
  v7 = a2;
  v32 = a2;
  v8 = a1;
  v31[0] = a3;
  v31[1] = a4;
  v34 = a6;
  v31[2] = 0;
  v30 = 0;
  v29 = 50;
  ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(68, &v30, v37, &v29);
  v10 = ThreadPreferredUILanguages;
  if ( !ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789 )
  {
    v11 = (wchar_t *)v37;
    v12 = 0;
    if ( v29 > 0x32 )
    {
      v13 = (wchar_t *)LocalAlloc(0x40u, 2LL * v29);
      v11 = v13;
      if ( !v13 )
        return (unsigned int)-1073741801;
      v12 = 1;
      v10 = RtlGetThreadPreferredUILanguages(68, &v30, v13, &v29);
      if ( v10 )
        goto LABEL_28;
    }
    v14 = -1;
    while ( v6 < 3 )
    {
      v15 = v31[v6];
      v16 = swprintf_s(Buffer, 0x32u, L"%x", v15);
      if ( v16 == -1 )
        break;
      v17 = 2LL * v16 + 2;
      if ( v17 >= 0x64 )
        _report_rangecheckfailure(v17);
      *(wchar_t *)((char *)Buffer + v17) = 0;
      if ( (int)RtlSetThreadPreferredUILanguages(4, Buffer, &v30) < 0 )
        break;
      MessageResourceEntry = 0;
      if ( RtlFindMessage(
             *((PVOID *)LsapPrivilegeDlls + 2 * v8 + 1),
             0xBu,
             0,
             (unsigned __int16)(v7 + 2),
             &MessageResourceEntry) >= 0 )
      {
        v18 = MessageResourceEntry;
        if ( (MessageResourceEntry->Flags & 1) != 0 )
        {
          do
            ++v14;
          while ( *(_WORD *)&MessageResourceEntry->Text[2 * v14] );
          if ( *(_WORD *)&MessageResourceEntry->Text[2 * (unsigned int)(v14 - 1)] == 10 )
          {
            v19 = (unsigned int)(v14 - 2);
            v20 = v19;
            if ( *(_WORD *)&MessageResourceEntry->Text[2 * v19] == 13 )
            {
              v21 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x10u);
              v22 = v21;
              if ( v21 )
              {
                v23 = 2 * v19;
                v21->Length = v23;
                v23 += 2;
                v21->MaximumLength = v23;
                v24 = (WCHAR *)LocalAlloc(0x40u, v23);
                v22->Buffer = v24;
                if ( v24 )
                {
                  memcpy_0(v24, v18->Text, v22->Length);
                  v25 = v34;
                  v22->Buffer[v20] = 0;
                  *v25 = v15;
                  *v35 = v22;
                }
                else
                {
                  LocalFree(v22);
                }
              }
            }
          }
          break;
        }
        v7 = v32;
      }
      ++v6;
    }
    if ( v29 )
    {
      v26 = v11;
      v27 = 4;
    }
    else
    {
      *(_DWORD *)Buffer = 0;
      v26 = Buffer;
      v27 = 0;
    }
    v10 = RtlSetThreadPreferredUILanguages(v27, v26, &v30);
    if ( v12 )
LABEL_28:
      LocalFree(v11);
  }
  return v10;
}

```

## disassembly

```asm
0x1801086d0  push    rbp
0x1801086d2  push    rbx
0x1801086d3  push    rsi
0x1801086d4  push    rdi
0x1801086d5  push    r12
0x1801086d7  push    r13
0x1801086d9  push    r14
0x1801086db  push    r15
0x1801086dd  lea     rbp, [rsp-58h]
0x1801086e2  sub     rsp, 158h
0x1801086e9  mov     rax, cs:__security_cookie
0x1801086f0  xor     rax, rsp
0x1801086f3  mov     [rbp+90h+var_50], rax
0x1801086f7  mov     rax, [rbp+90h+arg_20]
0x1801086fe  xor     edi, edi
0x180108700  mov     [rsp+190h+var_138], rax
0x180108705  mov     r14d, edx
0x180108708  mov     rax, [rbp+90h+arg_28]
0x18010870f  mov     [rsp+190h+var_150], edx
0x180108713  lea     rdx, [rsp+190h+var_15C]
0x180108718  mov     r15d, ecx
0x18010871b  lea     r13d, [rdi+44h]
0x18010871f  mov     [rsp+190h+var_158], r8w
0x180108725  mov     ecx, r13d
0x180108728  mov     [rsp+190h+var_156], r9w
0x18010872e  lea     r8, [rbp+90h+var_C0]
0x180108732  lea     r9, [rsp+190h+var_160]
0x180108737  mov     [rsp+190h+var_140], rax
0x18010873c  mov     [rsp+190h+var_154], di
0x180108741  mov     [rsp+190h+var_15C], edi
0x180108745  mov     [rsp+190h+var_160], 32h ; '2'
0x18010874d  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180108754  nop     dword ptr [rax+rax+00h]
0x180108759  mov     ebx, eax
0x18010875b  test    eax, eax
0x18010875d  jz      short loc_18010876A
0x18010875f  cmp     eax, 0C0000023h
0x180108764  jnz     loc_180108993
0x18010876a  cmp     [rsp+190h+var_160], 32h ; '2'
0x18010876f  lea     rsi, [rbp+90h+var_C0]
0x180108773  mov     r12b, dil
0x180108776  jbe     short loc_1801087CB
0x180108778  mov     edx, [rsp+190h+var_160]
0x18010877c  mov     ecx, 40h ; '@'; uFlags
0x180108781  add     rdx, rdx; uBytes
0x180108784  call    cs:__imp_LocalAlloc
0x18010878b  nop     dword ptr [rax+rax+00h]
0x180108790  mov     rsi, rax
0x180108793  test    rax, rax
0x180108796  jnz     short loc_1801087A2
0x180108798  mov     ebx, 0C0000017h
0x18010879d  jmp     loc_180108993
0x1801087a2  lea     r9, [rsp+190h+var_160]
0x1801087a7  mov     r8, rax
0x1801087aa  lea     rdx, [rsp+190h+var_15C]
0x1801087af  mov     ecx, r13d
0x1801087b2  mov     r12b, 1
0x1801087b5  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1801087bc  nop     dword ptr [rax+rax+00h]
0x1801087c1  mov     ebx, eax
0x1801087c3  test    eax, eax
0x1801087c5  jnz     loc_180108984
0x1801087cb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801087cf  cmp     edi, 3
0x1801087d2  jnb     loc_180108936
0x1801087d8  mov     eax, edi
0x1801087da  lea     r8, asc_18016D684; "%x"
0x1801087e1  mov     edx, 32h ; '2'; BufferCount
0x1801087e6  lea     rcx, [rsp+190h+Buffer]; Buffer
0x1801087eb  movzx   r13d, [rsp+rax*2+190h+var_158]
0x1801087f1  mov     r9d, r13d
0x1801087f4  call    swprintf_s
0x1801087f9  cmp     eax, ebx
0x1801087fb  jz      loc_180108936
0x180108801  cdqe
0x180108803  lea     rcx, ds:2[rax*2]
0x18010880b  cmp     rcx, 64h ; 'd'
0x18010880f  jnb     loc_18010895F
0x180108815  xor     eax, eax
0x180108817  lea     r8, [rsp+190h+var_15C]
0x18010881c  mov     [rsp+rcx+190h+Buffer], ax
0x180108821  lea     rdx, [rsp+190h+Buffer]
0x180108826  lea     ecx, [rax+4]
0x180108829  call    cs:__imp_RtlSetThreadPreferredUILanguages
0x180108830  nop     dword ptr [rax+rax+00h]
0x180108835  xor     ecx, ecx
0x180108837  test    eax, eax
0x180108839  js      loc_180108936
0x18010883f  mov     [rsp+190h+var_148], rcx
0x180108844  lea     eax, [r14+2]
0x180108848  movzx   r9d, ax; MessageId
0x18010884c  lea     rcx, [rsp+190h+var_148]
0x180108851  mov     [rsp+190h+MessageResourceEntry], rcx; MessageResourceEntry
0x180108856  xor     r8d, r8d; Language
0x180108859  mov     rcx, cs:?LsapPrivilegeDlls@@3PEAU_LSAP_DLL_DESCRIPTOR@@EA; _LSAP_DLL_DESCRIPTOR * LsapPrivilegeDlls
0x180108860  mov     rax, r15
0x180108863  add     rax, rax
0x180108866  lea     edx, [r8+0Bh]; Type
0x18010886a  mov     rcx, [rcx+rax*8+8]; BaseAddress
0x18010886f  call    cs:__imp_RtlFindMessage
0x180108876  nop     dword ptr [rax+rax+00h]
0x18010887b  xor     ecx, ecx
0x18010887d  test    eax, eax
0x18010887f  js      short loc_180108892
0x180108881  mov     r14, [rsp+190h+var_148]
0x180108886  test    byte ptr [r14+2], 1
0x18010888b  jnz     short loc_180108899
0x18010888d  mov     r14d, [rsp+190h+var_150]
0x180108892  inc     edi
0x180108894  jmp     loc_1801087CF
0x180108899  inc     rbx
0x18010889c  cmp     [r14+rbx*2+4], cx
0x1801088a2  jnz     short loc_180108899
0x1801088a4  lea     eax, [rbx-1]
0x1801088a7  cmp     word ptr [r14+rax*2+4], 0Ah
0x1801088ae  jnz     loc_180108936
0x1801088b4  lea     edi, [rbx-2]
0x1801088b7  cmp     word ptr [r14+rdi*2+4], 0Dh
0x1801088be  mov     r15d, edi
0x1801088c1  jnz     short loc_180108936
0x1801088c3  mov     edx, 10h; uBytes
0x1801088c8  lea     ecx, [rdx+30h]; uFlags
0x1801088cb  call    cs:__imp_LocalAlloc
0x1801088d2  nop     dword ptr [rax+rax+00h]
0x1801088d7  mov     rbx, rax
0x1801088da  test    rax, rax
0x1801088dd  jz      short loc_180108936
0x1801088df  add     di, di
0x1801088e2  mov     ecx, 40h ; '@'; uFlags
0x1801088e7  mov     [rax], di
0x1801088ea  add     di, 2
0x1801088ee  movzx   edx, di; uBytes
0x1801088f1  mov     [rax+2], dx
0x1801088f5  call    cs:__imp_LocalAlloc
0x1801088fc  nop     dword ptr [rax+rax+00h]
0x180108901  xor     edi, edi
0x180108903  mov     [rbx+8], rax
0x180108907  test    rax, rax
0x18010890a  jz      short loc_18010894E
0x18010890c  movzx   r8d, word ptr [rbx]; Size
0x180108910  lea     rdx, [r14+4]; Src
0x180108914  mov     rcx, rax; void *
0x180108917  call    memcpy_0
0x18010891c  mov     rcx, [rbx+8]
0x180108920  mov     rax, [rsp+190h+var_140]
0x180108925  mov     [rcx+r15*2], di
0x18010892a  mov     [rax], r13w
0x18010892e  mov     rax, [rsp+190h+var_138]
0x180108933  mov     [rax], rbx
0x180108936  xor     r13d, r13d
0x180108939  lea     r8, [rsp+190h+var_15C]
0x18010893e  cmp     [rsp+190h+var_160], r13d
0x180108943  jz      short loc_180108965
0x180108945  mov     rdx, rsi
0x180108948  lea     ecx, [r13+4]
0x18010894c  jmp     short loc_180108971
0x18010894e  mov     rcx, rbx; hMem
0x180108951  call    cs:__imp_LocalFree
0x180108958  nop     dword ptr [rax+rax+00h]
0x18010895d  jmp     short loc_180108936
0x18010895f  call    __report_rangecheckfailure
0x180108965  mov     dword ptr [rsp+190h+Buffer], r13d
0x18010896a  lea     rdx, [rsp+190h+Buffer]
0x18010896f  xor     ecx, ecx
0x180108971  call    cs:__imp_RtlSetThreadPreferredUILanguages
0x180108978  nop     dword ptr [rax+rax+00h]
0x18010897d  mov     ebx, eax
0x18010897f  test    r12b, r12b
0x180108982  jz      short loc_180108993
0x180108984  mov     rcx, rsi; hMem
0x180108987  call    cs:__imp_LocalFree
0x18010898e  nop     dword ptr [rax+rax+00h]
0x180108993  mov     eax, ebx
0x180108995  mov     rcx, [rbp+90h+var_50]
0x180108999  xor     rcx, rsp; StackCookie
0x18010899c  call    __security_check_cookie
0x1801089a1  add     rsp, 158h
0x1801089a8  pop     r15
0x1801089aa  pop     r14
0x1801089ac  pop     r13
0x1801089ae  pop     r12
0x1801089b0  pop     rdi
0x1801089b1  pop     rsi
0x1801089b2  pop     rbx
0x1801089b3  pop     rbp
0x1801089b4  retn
```
