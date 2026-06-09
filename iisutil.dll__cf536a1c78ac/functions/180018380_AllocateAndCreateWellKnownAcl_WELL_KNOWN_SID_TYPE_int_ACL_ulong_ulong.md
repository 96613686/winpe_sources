# AllocateAndCreateWellKnownAcl(WELL_KNOWN_SID_TYPE,int,_ACL * *,ulong *,ulong)

- ea: `0x180018380`
- end: `0x180018634`
- name: `?AllocateAndCreateWellKnownAcl@@YAKW4WELL_KNOWN_SID_TYPE@@HPEAPEAU_ACL@@PEAKK@Z`
- size: `692`
- prototype: `unsigned int __usercall@<eax>(enum WELL_KNOWN_SID_TYPE@<ecx>, int@<edx>, struct _ACL **@<r8>, unsigned int *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017ac0`
- `0x180018380`
- `0x180018ec0`
- `0x180024610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001856d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001856d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185bb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001849a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001849a`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x1800185ab`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x1800185ab`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180018559`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180018559`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800184ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800184ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018437`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018437`

## string_xrefs

- `0x180018414`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018485`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018406`: `AllocateAndCreateWellKnownAcl`
- `0x18001847e`: `AllocateAndCreateWellKnownAcl`
- `0x1800185de`: `Failure adding the access denied ace to the acl\n`
- `0x180018521`: `Failure initializing the acl\n`
- `0x180018590`: `Failure adding the access allowed ace to the acl\n`
- `0x1800183f6`: `Creating SID failed ( SidType = %d )\n`
- `0x1800184c3`: `Failure allocating space for the acl\n`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownAcl(
        __int32 a1,
        int a2,
        struct _ACL **a3,
        unsigned int *a4,
        DWORD AccessMask)
{
  char v8; // di
  signed int dwMessageId; // eax
  unsigned int v10; // ebx
  DWORD LengthSid; // eax
  DWORD v12; // esi
  struct _ACL *v13; // rax
  struct _ACL *v14; // rdi
  int v15; // eax
  int LastError; // eax
  int v17; // eax
  char v19; // [rsp+30h] [rbp-58h]
  struct _ACL *v20; // [rsp+40h] [rbp-48h] BYREF
  PSID pSid; // [rsp+A0h] [rbp+18h] BYREF

  pSid = 0;
  v20 = 0;
  v8 = a1;
  if ( !a3 || *a3 || !a4 )
    return 87;
  *a4 = 0;
  dwMessageId = AllocateAndCreateWellKnownSid((enum WELL_KNOWN_SID_TYPE)a1, &pSid);
  v10 = dwMessageId;
  if ( dwMessageId )
  {
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      if ( dwMessageId > 0 )
        dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        0x108u,
        "AllocateAndCreateWellKnownAcl",
        dwMessageId,
        "Creating SID failed ( SidType = %d )\n",
        v8);
    }
  }
  else
  {
    LengthSid = GetLengthSid(pSid);
    v12 = LengthSid + 16;
    if ( LengthSid < 0xFFFFFFF0 )
    {
      v13 = (struct _ACL *)GlobalAlloc(0, v12);
      v20 = v13;
      v14 = v13;
      if ( v13 )
      {
        if ( InitializeAcl(v13, v12, 2u) )
        {
          if ( a2 )
          {
            if ( !AddAccessAllowedAce(v14, 2u, AccessMask, pSid) )
            {
              LastError = GetLastError();
              v10 = LastError;
              if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
              {
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                PuDbgPrintError(
                  (struct _DEBUG_PRINTS *)g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                  0x15Au,
                  "AllocateAndCreateWellKnownAcl",
                  LastError,
                  "Failure adding the access allowed ace to the acl\n",
                  v19);
              }
              goto LABEL_33;
            }
          }
          else if ( !AddAccessDeniedAce(v14, 2u, AccessMask, pSid) )
          {
            v17 = GetLastError();
            v10 = v17;
            if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
            {
              if ( v17 > 0 )
                v17 = (unsigned __int16)v17 | 0x80070000;
              PuDbgPrintError(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
                0x16Au,
                "AllocateAndCreateWellKnownAcl",
                v17,
                "Failure adding the access denied ace to the acl\n",
                v19);
            }
            goto LABEL_33;
          }
          *a3 = v14;
          *a4 = v12;
        }
        else
        {
          v15 = GetLastError();
          v10 = v15;
          if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          {
            if ( v15 > 0 )
              v15 = (unsigned __int16)v15 | 0x80070000;
            PuDbgPrintError(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
              0x148u,
              "AllocateAndCreateWellKnownAcl",
              v15,
              "Failure initializing the acl\n",
              v19);
          }
        }
      }
      else
      {
        v10 = 14;
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
            0x139u,
            "AllocateAndCreateWellKnownAcl",
            0x8007000E,
            "Failure allocating space for the acl\n",
            v19);
      }
    }
    else
    {
      v10 = 534;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          0x12Au,
          "AllocateAndCreateWellKnownAcl",
          0x80070216,
          "Arithematic overflow detected.\n",
          v19);
    }
  }
LABEL_33:
  FreeWellKnownAcl((struct _ACL **)&pSid);
  if ( !*a3 )
    FreeWellKnownAcl(&v20);
  return v10;
}

```

## disassembly

```asm
0x180018380  mov     rax, rsp
0x180018383  push    rbx
0x180018384  push    rsi
0x180018385  push    rdi
0x180018386  push    r12
0x180018388  push    r14
0x18001838a  push    r15
0x18001838c  sub     rsp, 58h
0x180018390  mov     qword ptr [rax+18h], 0
0x180018398  mov     r14, r9
0x18001839b  mov     qword ptr [rax-48h], 0
0x1800183a3  mov     r15, r8
0x1800183a6  mov     r12d, edx
0x1800183a9  mov     edi, ecx
0x1800183ab  test    r8, r8
0x1800183ae  jz      loc_180018620
0x1800183b4  cmp     qword ptr [r8], 0
0x1800183b8  jnz     loc_180018620
0x1800183be  test    r9, r9
0x1800183c1  jz      loc_180018620
0x1800183c7  lea     rdx, [rax+18h]; void **
0x1800183cb  mov     dword ptr [r9], 0
0x1800183d2  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800183d7  mov     ebx, eax
0x1800183d9  test    eax, eax
0x1800183db  jz      short loc_18001842F
0x1800183dd  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800183e4  jz      loc_1800185FF
0x1800183ea  test    eax, eax
0x1800183ec  jle     short loc_1800183F6
0x1800183ee  movzx   eax, ax
0x1800183f1  or      eax, 80070000h
0x1800183f6  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x1800183fd  mov     dword ptr [rsp+88h+var_58], edi; char
0x180018401  mov     [rsp+88h+var_60], rcx; char *
0x180018406  lea     r9, aAllocateandcre_1; "AllocateAndCreateWellKnownAcl"
0x18001840d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018414  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001841b  mov     r8d, 108h; unsigned int
0x180018421  mov     [rsp+88h+dwMessageId], eax; dwMessageId
0x180018425  call    PuDbgPrintError
0x18001842a  jmp     loc_1800185FF
0x18001842f  mov     rcx, [rsp+88h+pSid]; pSid
0x180018437  call    cs:__imp_GetLengthSid
0x18001843e  nop     dword ptr [rax+rax+00h]
0x180018443  lea     esi, [rax+10h]
0x180018446  cmp     esi, 10h
0x180018449  jnb     short loc_180018496
0x18001844b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018452  mov     ebx, 216h
0x180018457  jz      loc_1800185FF
0x18001845d  lea     rax, aArithematicOve; "Arithematic overflow detected.\n"
0x180018464  mov     r8d, 12Ah; unsigned int
0x18001846a  mov     [rsp+88h+var_60], rax; char *
0x18001846f  mov     [rsp+88h+dwMessageId], 80070216h; dwMessageId
0x180018477  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001847e  lea     r9, aAllocateandcre_1; "AllocateAndCreateWellKnownAcl"
0x180018485  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001848c  call    PuDbgPrintError
0x180018491  jmp     loc_1800185FF
0x180018496  mov     edx, esi; dwBytes
0x180018498  xor     ecx, ecx; uFlags
0x18001849a  call    cs:__imp_GlobalAlloc
0x1800184a1  nop     dword ptr [rax+rax+00h]
0x1800184a6  mov     [rsp+88h+var_48], rax
0x1800184ab  mov     rdi, rax
0x1800184ae  test    rax, rax
0x1800184b1  jnz     short loc_1800184DF
0x1800184b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800184ba  lea     ebx, [rax+0Eh]
0x1800184bd  jz      loc_1800185FF
0x1800184c3  lea     rax, aFailureAllocat; "Failure allocating space for the acl\n"
0x1800184ca  mov     r8d, 139h
0x1800184d0  mov     [rsp+88h+var_60], rax
0x1800184d5  mov     [rsp+88h+dwMessageId], 8007000Eh
0x1800184dd  jmp     short loc_180018477
0x1800184df  mov     r8d, 2; dwAclRevision
0x1800184e5  mov     edx, esi; nAclLength
0x1800184e7  mov     rcx, rdi; pAcl
0x1800184ea  call    cs:__imp_InitializeAcl
0x1800184f1  nop     dword ptr [rax+rax+00h]
0x1800184f6  test    eax, eax
0x1800184f8  jnz     short loc_18001853C
0x1800184fa  call    cs:__imp_GetLastError
0x180018501  nop     dword ptr [rax+rax+00h]
0x180018506  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001850d  mov     ebx, eax
0x18001850f  jz      loc_1800185FF
0x180018515  test    eax, eax
0x180018517  jle     short loc_180018521
0x180018519  movzx   eax, ax
0x18001851c  or      eax, 80070000h
0x180018521  lea     rcx, aFailureInitial; "Failure initializing the acl\n"
0x180018528  mov     r8d, 148h
0x18001852e  mov     [rsp+88h+var_60], rcx
0x180018533  mov     [rsp+88h+dwMessageId], eax
0x180018537  jmp     loc_180018477
0x18001853c  mov     r9, [rsp+88h+pSid]; pSid
0x180018544  mov     edx, 2; dwAceRevision
0x180018549  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x180018551  mov     rcx, rdi; pAcl
0x180018554  test    r12d, r12d
0x180018557  jz      short loc_1800185AB
0x180018559  call    cs:__imp_AddAccessAllowedAce
0x180018560  nop     dword ptr [rax+rax+00h]
0x180018565  test    eax, eax
0x180018567  jnz     loc_1800185F9
0x18001856d  call    cs:__imp_GetLastError
0x180018574  nop     dword ptr [rax+rax+00h]
0x180018579  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018580  mov     ebx, eax
0x180018582  jz      short loc_1800185FF
0x180018584  test    eax, eax
0x180018586  jle     short loc_180018590
0x180018588  movzx   eax, ax
0x18001858b  or      eax, 80070000h
0x180018590  lea     rcx, aFailureAddingT_0; "Failure adding the access allowed ace t"...
0x180018597  mov     r8d, 15Ah
0x18001859d  mov     [rsp+88h+var_60], rcx
0x1800185a2  mov     [rsp+88h+dwMessageId], eax
0x1800185a6  jmp     loc_180018477
0x1800185ab  call    cs:__imp_AddAccessDeniedAce
0x1800185b2  nop     dword ptr [rax+rax+00h]
0x1800185b7  test    eax, eax
0x1800185b9  jnz     short loc_1800185F9
0x1800185bb  call    cs:__imp_GetLastError
0x1800185c2  nop     dword ptr [rax+rax+00h]
0x1800185c7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800185ce  mov     ebx, eax
0x1800185d0  jz      short loc_1800185FF
0x1800185d2  test    eax, eax
0x1800185d4  jle     short loc_1800185DE
0x1800185d6  movzx   eax, ax
0x1800185d9  or      eax, 80070000h
0x1800185de  lea     rcx, aFailureAddingT; "Failure adding the access denied ace to"...
0x1800185e5  mov     r8d, 16Ah
0x1800185eb  mov     [rsp+88h+var_60], rcx
0x1800185f0  mov     [rsp+88h+dwMessageId], eax
0x1800185f4  jmp     loc_180018477
0x1800185f9  mov     [r15], rdi
0x1800185fc  mov     [r14], esi
0x1800185ff  lea     rcx, [rsp+88h+pSid]; struct _ACL **
0x180018607  call    ?FreeWellKnownAcl@@YAXPEAPEAU_ACL@@@Z; FreeWellKnownAcl(_ACL * *)
0x18001860c  cmp     qword ptr [r15], 0
0x180018610  jnz     short loc_18001861C
0x180018612  lea     rcx, [rsp+88h+var_48]; struct _ACL **
0x180018617  call    ?FreeWellKnownAcl@@YAXPEAPEAU_ACL@@@Z; FreeWellKnownAcl(_ACL * *)
0x18001861c  mov     eax, ebx
0x18001861e  jmp     short loc_180018625
0x180018620  mov     eax, 57h ; 'W'
0x180018625  add     rsp, 58h
0x180018629  pop     r15
0x18001862b  pop     r14
0x18001862d  pop     r12
0x18001862f  pop     rdi
0x180018630  pop     rsi
0x180018631  pop     rbx
0x180018632  retn
```
