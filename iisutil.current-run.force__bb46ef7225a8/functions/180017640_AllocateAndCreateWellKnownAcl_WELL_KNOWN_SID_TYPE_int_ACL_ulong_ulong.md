# AllocateAndCreateWellKnownAcl(WELL_KNOWN_SID_TYPE,int,_ACL * *,ulong *,ulong)

- ea: `0x180017640`
- end: `0x1800178bf`
- name: `?AllocateAndCreateWellKnownAcl@@YAKW4WELL_KNOWN_SID_TYPE@@HPEAPEAU_ACL@@PEAKK@Z`
- size: `639`
- prototype: `unsigned int __usercall@<eax>(enum WELL_KNOWN_SID_TYPE@<ecx>, int@<edx>, struct _ACL **@<r8>, unsigned int *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016e40`
- `0x180017640`
- `0x1800180c0`
- `0x180022da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001780b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001784d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001780b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001784d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180017754`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180017754`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180017843`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180017843`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017801`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180017801`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001779e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001779e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800176f7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800176f7`

## string_xrefs

- `0x1800176d4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x18001773f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x1800176c6`: `AllocateAndCreateWellKnownAcl`
- `0x180017738`: `AllocateAndCreateWellKnownAcl`
- `0x18001786a`: `Failure adding the access denied ace to the acl\n`
- `0x1800177c9`: `Failure initializing the acl\n`
- `0x180017828`: `Failure adding the access allowed ace to the acl\n`
- `0x1800176b6`: `Creating SID failed ( SidType = %d )\n`
- `0x180017777`: `Failure allocating space for the acl\n`

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
0x180017640  mov     rax, rsp
0x180017643  push    rbx
0x180017644  push    rsi
0x180017645  push    rdi
0x180017646  push    r12
0x180017648  push    r14
0x18001764a  push    r15
0x18001764c  sub     rsp, 58h
0x180017650  mov     qword ptr [rax+18h], 0
0x180017658  mov     r14, r9
0x18001765b  mov     qword ptr [rax-48h], 0
0x180017663  mov     r15, r8
0x180017666  mov     r12d, edx
0x180017669  mov     edi, ecx
0x18001766b  test    r8, r8
0x18001766e  jz      loc_1800178AC
0x180017674  cmp     qword ptr [r8], 0
0x180017678  jnz     loc_1800178AC
0x18001767e  test    r9, r9
0x180017681  jz      loc_1800178AC
0x180017687  lea     rdx, [rax+18h]; void **
0x18001768b  mov     dword ptr [r9], 0
0x180017692  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180017697  mov     ebx, eax
0x180017699  test    eax, eax
0x18001769b  jz      short loc_1800176EF
0x18001769d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800176a4  jz      loc_18001788B
0x1800176aa  test    eax, eax
0x1800176ac  jle     short loc_1800176B6
0x1800176ae  movzx   eax, ax
0x1800176b1  or      eax, 80070000h
0x1800176b6  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x1800176bd  mov     dword ptr [rsp+88h+var_58], edi; char
0x1800176c1  mov     [rsp+88h+var_60], rcx; char *
0x1800176c6  lea     r9, aAllocateandcre_1; "AllocateAndCreateWellKnownAcl"
0x1800176cd  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800176d4  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800176db  mov     r8d, 108h; unsigned int
0x1800176e1  mov     [rsp+88h+dwMessageId], eax; dwMessageId
0x1800176e5  call    PuDbgPrintError
0x1800176ea  jmp     loc_18001788B
0x1800176ef  mov     rcx, [rsp+88h+pSid]; pSid
0x1800176f7  call    cs:__imp_GetLengthSid
0x1800176fd  lea     esi, [rax+10h]
0x180017700  cmp     esi, 10h
0x180017703  jnb     short loc_180017750
0x180017705  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001770c  mov     ebx, 216h
0x180017711  jz      loc_18001788B
0x180017717  lea     rax, aArithematicOve; "Arithematic overflow detected.\n"
0x18001771e  mov     r8d, 12Ah; unsigned int
0x180017724  mov     [rsp+88h+var_60], rax; char *
0x180017729  mov     [rsp+88h+dwMessageId], 80070216h; dwMessageId
0x180017731  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017738  lea     r9, aAllocateandcre_1; "AllocateAndCreateWellKnownAcl"
0x18001773f  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017746  call    PuDbgPrintError
0x18001774b  jmp     loc_18001788B
0x180017750  mov     edx, esi; dwBytes
0x180017752  xor     ecx, ecx; uFlags
0x180017754  call    cs:__imp_GlobalAlloc
0x18001775a  mov     [rsp+88h+var_48], rax
0x18001775f  mov     rdi, rax
0x180017762  test    rax, rax
0x180017765  jnz     short loc_180017793
0x180017767  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001776e  lea     ebx, [rax+0Eh]
0x180017771  jz      loc_18001788B
0x180017777  lea     rax, aFailureAllocat; "Failure allocating space for the acl\n"
0x18001777e  mov     r8d, 139h
0x180017784  mov     [rsp+88h+var_60], rax
0x180017789  mov     [rsp+88h+dwMessageId], 8007000Eh
0x180017791  jmp     short loc_180017731
0x180017793  mov     r8d, 2; dwAclRevision
0x180017799  mov     edx, esi; nAclLength
0x18001779b  mov     rcx, rdi; pAcl
0x18001779e  call    cs:__imp_InitializeAcl
0x1800177a4  test    eax, eax
0x1800177a6  jnz     short loc_1800177E4
0x1800177a8  call    cs:__imp_GetLastError
0x1800177ae  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800177b5  mov     ebx, eax
0x1800177b7  jz      loc_18001788B
0x1800177bd  test    eax, eax
0x1800177bf  jle     short loc_1800177C9
0x1800177c1  movzx   eax, ax
0x1800177c4  or      eax, 80070000h
0x1800177c9  lea     rcx, aFailureInitial; "Failure initializing the acl\n"
0x1800177d0  mov     r8d, 148h
0x1800177d6  mov     [rsp+88h+var_60], rcx
0x1800177db  mov     [rsp+88h+dwMessageId], eax
0x1800177df  jmp     loc_180017731
0x1800177e4  mov     r9, [rsp+88h+pSid]; pSid
0x1800177ec  mov     edx, 2; dwAceRevision
0x1800177f1  mov     r8d, [rsp+88h+AccessMask]; AccessMask
0x1800177f9  mov     rcx, rdi; pAcl
0x1800177fc  test    r12d, r12d
0x1800177ff  jz      short loc_180017843
0x180017801  call    cs:__imp_AddAccessAllowedAce
0x180017807  test    eax, eax
0x180017809  jnz     short loc_180017885
0x18001780b  call    cs:__imp_GetLastError
0x180017811  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017818  mov     ebx, eax
0x18001781a  jz      short loc_18001788B
0x18001781c  test    eax, eax
0x18001781e  jle     short loc_180017828
0x180017820  movzx   eax, ax
0x180017823  or      eax, 80070000h
0x180017828  lea     rcx, aFailureAddingT_0; "Failure adding the access allowed ace t"...
0x18001782f  mov     r8d, 15Ah
0x180017835  mov     [rsp+88h+var_60], rcx
0x18001783a  mov     [rsp+88h+dwMessageId], eax
0x18001783e  jmp     loc_180017731
0x180017843  call    cs:__imp_AddAccessDeniedAce
0x180017849  test    eax, eax
0x18001784b  jnz     short loc_180017885
0x18001784d  call    cs:__imp_GetLastError
0x180017853  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001785a  mov     ebx, eax
0x18001785c  jz      short loc_18001788B
0x18001785e  test    eax, eax
0x180017860  jle     short loc_18001786A
0x180017862  movzx   eax, ax
0x180017865  or      eax, 80070000h
0x18001786a  lea     rcx, aFailureAddingT; "Failure adding the access denied ace to"...
0x180017871  mov     r8d, 16Ah
0x180017877  mov     [rsp+88h+var_60], rcx
0x18001787c  mov     [rsp+88h+dwMessageId], eax
0x180017880  jmp     loc_180017731
0x180017885  mov     [r15], rdi
0x180017888  mov     [r14], esi
0x18001788b  lea     rcx, [rsp+88h+pSid]; struct _ACL **
0x180017893  call    ?FreeWellKnownAcl@@YAXPEAPEAU_ACL@@@Z; FreeWellKnownAcl(_ACL * *)
0x180017898  cmp     qword ptr [r15], 0
0x18001789c  jnz     short loc_1800178A8
0x18001789e  lea     rcx, [rsp+88h+var_48]; struct _ACL **
0x1800178a3  call    ?FreeWellKnownAcl@@YAXPEAPEAU_ACL@@@Z; FreeWellKnownAcl(_ACL * *)
0x1800178a8  mov     eax, ebx
0x1800178aa  jmp     short loc_1800178B1
0x1800178ac  mov     eax, 57h ; 'W'
0x1800178b1  add     rsp, 58h
0x1800178b5  pop     r15
0x1800178b7  pop     r14
0x1800178b9  pop     r12
0x1800178bb  pop     rdi
0x1800178bc  pop     rsi
0x1800178bd  pop     rbx
0x1800178be  retn
```
