# CscDclpGetFsctlOperationString

- ea: `0x1400623f4`
- end: `0x1400628a3`
- name: `CscDclpGetFsctlOperationString`
- size: `1199`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14007ae70`
- `0x14007cd30`

## callees

- `0x1400623f4`

## string_xrefs

- `0x140062477`: `CSC_FSCTL_OPERATION_DELETE`
- `0x140062453`: `CSC_FSCTL_OPERATION_QUERY_SECURITY`
- `0x14006245c`: `CSC_FSCTL_OPERATION_RENAME`
- `0x1400624a4`: `CSC_FSCTL_OPERATION_SET_SECURITY`
- `0x140062504`: `CSC_FSCTL_OPERATION_QUERY_DIRECTORY`
- `0x14006250d`: `CSC_FSCTL_OPERATION_REMOVE_PIN`
- `0x1400625a9`: `CSC_FSCTL_OPERATION_PRINCIPAL_ID_TO_SID`
- `0x14006263a`: `CSC_FSCTL_OPERATION_DELETE_CREDENTIAL`
- `0x14006260d`: `CSC_FSCTL_OPERATION_GET_SID_INDEX`
- `0x140062604`: `CSC_FSCTL_OPERATION_ADD_SID`
- `0x1400626ca`: `CSC_FSCTL_OPERATION_IMPORT_QUERY_TEMP_NAME`
- `0x1400626af`: `CSC_FSCTL_OPERATION_UPDATE_SUSPENDED_ITEM`
- `0x1400626b8`: `CSC_FSCTL_OPERATION_CREATE_REPLACE_DATA_FOR_SUSPENDED_ITEM`
- `0x14006275b`: `CSC_FSCTL_OPERATION_REPLACE_SID`
- `0x140062752`: `CSC_FSCTL_OPERATION_REBOOT_RENAME_ADD`
- `0x140062737`: `CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_RENAME_ENABLE_ON_PATHS`
- `0x140062740`: `CSC_FSCTL_OPERATION_KNOWN_OFFLINE_PATH`
- `0x14006272e`: `CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_RENAME_REMOVE_PATHS`
- `0x1400627dc`: `CSC_FSCTL_OPERATION_WRITE_STORE_DATA`
- `0x140062865`: `CSC_FSCTL_OPERATION_PURGE_OFFLINE_LVIEW_CACHE`
- `0x14006286e`: `CSC_FSCTL_OPERATION_QUERY_FAILED_TRANSITION_PATH`

## pseudocode

```c
const char *__fastcall CscDclpGetFsctlOperationString(int a1)
{
  if ( a1 > 38 )
  {
    if ( a1 > 57 )
    {
      if ( a1 > 67 )
      {
        switch ( a1 )
        {
          case 'D':
            return "CSC_FSCTL_OPERATION_QUERY_ITEM_EXTENDED";
          case 'E':
            return "CSC_FSCTL_OPERATION_GET_PEER_CACHING_ENABLED";
          case 'F':
            return "CSC_FSCTL_OPERATION_RESET_PERFCOUNTERS";
          case 'G':
            return "CSC_FSCTL_OPERATION_QUERY_HASH_CAPABILITIES";
          case 'H':
            return "CSC_FSCTL_OPERATION_SET_CACHING_ENABLED";
          case 'I':
            return "CSC_FSCTL_OPERATION_QUERY_FAILED_TRANSITION_PATH";
          case 'J':
            return "CSC_FSCTL_OPERATION_PURGE_OFFLINE_LVIEW_CACHE";
          case 'K':
            return "CSC_FSCTL_OPERATION_INVALID";
          default:
            return "*INVALID*";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 'C':
            return "CSC_FSCTL_OPERATION_GET_CONNECTION_PERF";
          case ':':
            return "CSC_FSCTL_OPERATION_QUERY_CLIENT_OPLOCK_STATE";
          case ';':
            return "CSC_FSCTL_OPERATION_SET_EXCLUDED_FILE_TYPES";
          case '<':
            return "CSC_FSCTL_OPERATION_SET_TRANSPARENT_CACHING_LATENCY";
          case '=':
            return "CSC_FSCTL_OPERATION_SET_PEER_CACHING_ENABLED";
          case '>':
            return "CSC_FSCTL_OPERATION_QUERY_PERFCOUNTERS";
          case '?':
            return "CSC_FSCTL_OPERATION_WRITE_STORE_DATA";
          case '@':
            return "CSC_FSCTL_OPERATION_RETRIEVE_HASH_DATA";
          case 'A':
            return "CSC_FSCTL_OPERATION_SET_PREFETCH";
          default:
            return "CSC_FSCTL_OPERATION_CLEAR_CONNECTION_PERF";
        }
      }
    }
    else if ( a1 == 57 )
    {
      return "CSC_FSCTL_OPERATION_CONVERT_BACKOUT_HANDLE";
    }
    else if ( a1 > 48 )
    {
      switch ( a1 )
      {
        case '1':
          return "CSC_FSCTL_OPERATION_SET_SPARSE_EXCLUSION_LIST";
        case '2':
          return "CSC_FSCTL_OPERATION_FLUSH_PRIORITY_QUEUE";
        case '3':
          return "CSC_FSCTL_OPERATION_REPLACE_SID";
        case '4':
          return "CSC_FSCTL_OPERATION_REBOOT_RENAME_ADD";
        case '5':
          return "CSC_FSCTL_OPERATION_TEST";
        case '6':
          return "CSC_FSCTL_OPERATION_KNOWN_OFFLINE_PATH";
        case '7':
          return "CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_RENAME_ENABLE_ON_PATHS";
        default:
          return "CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_RENAME_REMOVE_PATHS";
      }
    }
    else
    {
      switch ( a1 )
      {
        case '0':
          return "CSC_FSCTL_OPERATION_SET_CONNECTION_PERF";
        case '\'':
          return "CSC_FSCTL_OPERATION_IMPORT_ASSOCIATE_HANDLE";
        case '(':
          return "CSC_FSCTL_OPERATION_IMPORT_END";
        case ')':
          return "CSC_FSCTL_OPERATION_IMPORT_ITEM";
        case '*':
          return "CSC_FSCTL_OPERATION_IMPORT_FILE";
        case '+':
          return "CSC_FSCTL_OPERATION_IMPORT_QUERY_TEMP_NAME";
        case ',':
          return "CSC_FSCTL_OPERATION_IMPORT_QUERY_GATHERED_STORE_VERSION";
        case '-':
          return "CSC_FSCTL_OPERATION_CREATE_REPLACE_DATA_FOR_SUSPENDED_ITEM";
        case '.':
          return "CSC_FSCTL_OPERATION_UPDATE_SUSPENDED_ITEM";
        default:
          return "CSC_FSCTL_OPERATION_CONTROL_FAULT_INJECTION";
      }
    }
  }
  else
  {
    if ( a1 == 38 )
      return "CSC_FSCTL_OPERATION_IMPORT_START";
    if ( a1 > 19 )
    {
      if ( a1 > 29 )
      {
        switch ( a1 )
        {
          case 30:
            return "CSC_FSCTL_OPERATION_UPCALL_REPLY";
          case 31:
            return "CSC_FSCTL_OPERATION_DELETE_CREDENTIAL";
          case 32:
            return "CSC_FSCTL_OPERATION_HAS_CREDENTIAL_ERROR";
          case 33:
            return "CSC_FSCTL_OPERATION_ENCRYPT_DECRYPT";
          case 34:
            return "CSC_FSCTL_OPERATION_EXTRACT_DIR";
          case 35:
            return "CSC_FSCTL_OPERATION_EXTRACT_QUERY_ITEM_LOCATION";
          case 36:
            return "CSC_FSCTL_OPERATION_GET_SID_INDEX";
          default:
            return "CSC_FSCTL_OPERATION_ADD_SID";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 29:
            return "CSC_FSCTL_OPERATION_UPCALL_RECEIVE";
          case 20:
            return "CSC_FSCTL_OPERATION_SET_DATABASE_EVICTION_PERIOD";
          case 21:
            return "CSC_FSCTL_OPERATION_QUERY_LOCATION_DATABASE";
          case 22:
            return "CSC_FSCTL_OPERATION_SET_LOCATION_DATABASE";
          case 23:
            return "CSC_FSCTL_OPERATION_PRINCIPAL_ID_TO_SID";
          case 24:
            return "CSC_FSCTL_OPERATION_CONNECT";
          case 25:
            return "CSC_FSCTL_OPERATION_DISCONNECT";
          case 26:
            return "CSC_FSCTL_OPERATION_ENABLE";
          case 27:
            return "CSC_FSCTL_OPERATION_DISABLE";
          default:
            return "CSC_FSCTL_OPERATION_IS_ENABLED";
        }
      }
    }
    else
    {
      if ( a1 == 19 )
        return "CSC_FSCTL_OPERATION_QUERY_DATABASE_EVICTION_PERIOD";
      if ( a1 <= 9 )
      {
        switch ( a1 )
        {
          case 9:
            return "CSC_FSCTL_OPERATION_SET_SECURITY";
          case 0:
            return "CSC_FSCTL_OPERATION_QUERY_HANDLE";
          case 1:
            return "CSC_FSCTL_OPERATION_TRANSITION";
          case 2:
            return "CSC_FSCTL_OPERATION_QUERY_ITEM";
          case 3:
            return "CSC_FSCTL_OPERATION_SET_ITEM";
          case 4:
            return "CSC_FSCTL_OPERATION_DELETE";
          case 5:
            return "CSC_FSCTL_OPERATION_EVICT_ITEM";
          case 6:
            return "CSC_FSCTL_OPERATION_EVICT";
          case 7:
            return "CSC_FSCTL_OPERATION_RENAME";
          case 8:
            return "CSC_FSCTL_OPERATION_QUERY_SECURITY";
        }
        return "*INVALID*";
      }
      switch ( a1 )
      {
        case 10:
          return "CSC_FSCTL_OPERATION_QUERY_PIN";
        case 11:
          return "CSC_FSCTL_OPERATION_QUERY_PIN_ALL";
        case 12:
          return "CSC_FSCTL_OPERATION_SET_PIN";
        case 13:
          return "CSC_FSCTL_OPERATION_REMOVE_PIN";
        case 14:
          return "CSC_FSCTL_OPERATION_QUERY_DIRECTORY";
        case 15:
          return "CSC_OPERATION_QUERY_DIFF_TRANSFER_OFFSET";
        case 16:
          return "CSC_FSCTL_OPERATION_ENUMERATE_QUEUE";
        case 17:
          return "CSC_FSCTL_OPERATION_QUERY_DATABASE";
        default:
          return "CSC_FSCTL_OPERATION_SET_DATABASE";
      }
    }
  }
}

```

## disassembly

```asm
0x1400623f4  cmp     ecx, 26h ; '&'
0x1400623f7  jg      loc_140062655
0x1400623fd  jz      loc_14006264C
0x140062403  cmp     ecx, 13h
0x140062406  jg      loc_14006253A
0x14006240c  jz      loc_140062531
0x140062412  cmp     ecx, 9
0x140062415  jg      loc_1400624AD
0x14006241b  jz      loc_1400624A4
0x140062421  mov     edx, ecx
0x140062423  test    ecx, ecx
0x140062425  jz      short loc_14006249B
0x140062427  sub     edx, 1
0x14006242a  jz      short loc_140062492
0x14006242c  sub     edx, 1
0x14006242f  jz      short loc_140062489
0x140062431  sub     edx, 1
0x140062434  jz      short loc_140062480
0x140062436  sub     edx, 1
0x140062439  jz      short loc_140062477
0x14006243b  sub     edx, 1
0x14006243e  jz      short loc_14006246E
0x140062440  sub     edx, 1
0x140062443  jz      short loc_140062465
0x140062445  sub     edx, 1
0x140062448  jz      short loc_14006245C
0x14006244a  cmp     edx, 1
0x14006244d  jnz     loc_140062845
0x140062453  lea     rax, aCscFsctlOperat_53; "CSC_FSCTL_OPERATION_QUERY_SECURITY"
0x14006245a  retn
0x14006245c  lea     rax, aCscFsctlOperat_62; "CSC_FSCTL_OPERATION_RENAME"
0x140062463  retn
0x140062465  lea     rax, aCscFsctlOperat; "CSC_FSCTL_OPERATION_EVICT"
0x14006246c  retn
0x14006246e  lea     rax, aCscFsctlOperat_12; "CSC_FSCTL_OPERATION_EVICT_ITEM"
0x140062475  retn
0x140062477  lea     rax, aCscFsctlOperat_7; "CSC_FSCTL_OPERATION_DELETE"
0x14006247e  retn
0x140062480  lea     rax, aCscFsctlOperat_72; "CSC_FSCTL_OPERATION_SET_ITEM"
0x140062487  retn
0x140062489  lea     rax, aCscFsctlOperat_58; "CSC_FSCTL_OPERATION_QUERY_ITEM"
0x140062490  retn
0x140062492  lea     rax, aCscFsctlOperat_33; "CSC_FSCTL_OPERATION_TRANSITION"
0x140062499  retn
0x14006249b  lea     rax, aCscFsctlOperat_10; "CSC_FSCTL_OPERATION_QUERY_HANDLE"
0x1400624a2  retn
0x1400624a4  lea     rax, aCscFsctlOperat_26; "CSC_FSCTL_OPERATION_SET_SECURITY"
0x1400624ab  retn
0x1400624ad  mov     edx, ecx
0x1400624af  sub     edx, 0Ah
0x1400624b2  jz      short loc_140062528
0x1400624b4  sub     edx, 1
0x1400624b7  jz      short loc_14006251F
0x1400624b9  sub     edx, 1
0x1400624bc  jz      short loc_140062516
0x1400624be  sub     edx, 1
0x1400624c1  jz      short loc_14006250D
0x1400624c3  sub     edx, 1
0x1400624c6  jz      short loc_140062504
0x1400624c8  sub     edx, 1
0x1400624cb  jz      short loc_1400624FB
0x1400624cd  sub     edx, 1
0x1400624d0  jz      short loc_1400624F2
0x1400624d2  sub     edx, 1
0x1400624d5  jz      short loc_1400624E9
0x1400624d7  cmp     edx, 1
0x1400624da  jnz     loc_140062845
0x1400624e0  lea     rax, aCscFsctlOperat_36; "CSC_FSCTL_OPERATION_SET_DATABASE"
0x1400624e7  retn
0x1400624e9  lea     rax, aCscFsctlOperat_14; "CSC_FSCTL_OPERATION_QUERY_DATABASE"
0x1400624f0  retn
0x1400624f2  lea     rax, aCscFsctlOperat_11; "CSC_FSCTL_OPERATION_ENUMERATE_QUEUE"
0x1400624f9  retn
0x1400624fb  lea     rax, aCscOperationQu; "CSC_OPERATION_QUERY_DIFF_TRANSFER_OFFSE"...
0x140062502  retn
0x140062504  lea     rax, aCscFsctlOperat_73; "CSC_FSCTL_OPERATION_QUERY_DIRECTORY"
0x14006250b  retn
0x14006250d  lea     rax, aCscFsctlOperat_27; "CSC_FSCTL_OPERATION_REMOVE_PIN"
0x140062514  retn
0x140062516  lea     rax, aCscFsctlOperat_30; "CSC_FSCTL_OPERATION_SET_PIN"
0x14006251d  retn
0x14006251f  lea     rax, aCscFsctlOperat_41; "CSC_FSCTL_OPERATION_QUERY_PIN_ALL"
0x140062526  retn
0x140062528  lea     rax, aCscFsctlOperat_5; "CSC_FSCTL_OPERATION_QUERY_PIN"
0x14006252f  retn
0x140062531  lea     rax, aCscFsctlOperat_25; "CSC_FSCTL_OPERATION_QUERY_DATABASE_EVIC"...
0x140062538  retn
0x14006253a  cmp     ecx, 1Dh
0x14006253d  jg      loc_1400625D6
0x140062543  jz      loc_1400625CD
0x140062549  mov     edx, ecx
0x14006254b  sub     edx, 14h
0x14006254e  jz      short loc_1400625C4
0x140062550  sub     edx, 1
0x140062553  jz      short loc_1400625BB
0x140062555  sub     edx, 1
0x140062558  jz      short loc_1400625B2
0x14006255a  sub     edx, 1
0x14006255d  jz      short loc_1400625A9
0x14006255f  sub     edx, 1
0x140062562  jz      short loc_1400625A0
0x140062564  sub     edx, 1
0x140062567  jz      short loc_140062597
0x140062569  sub     edx, 1
0x14006256c  jz      short loc_14006258E
0x14006256e  sub     edx, 1
0x140062571  jz      short loc_140062585
0x140062573  cmp     edx, 1
0x140062576  jnz     loc_140062845
0x14006257c  lea     rax, aCscFsctlOperat_70; "CSC_FSCTL_OPERATION_IS_ENABLED"
0x140062583  retn
0x140062585  lea     rax, aCscFsctlOperat_34; "CSC_FSCTL_OPERATION_DISABLE"
0x14006258c  retn
0x14006258e  lea     rax, aCscFsctlOperat_37; "CSC_FSCTL_OPERATION_ENABLE"
0x140062595  retn
0x140062597  lea     rax, aCscFsctlOperat_22; "CSC_FSCTL_OPERATION_DISCONNECT"
0x14006259e  retn
0x1400625a0  lea     rax, aCscFsctlOperat_17; "CSC_FSCTL_OPERATION_CONNECT"
0x1400625a7  retn
0x1400625a9  lea     rax, aCscFsctlOperat_2; "CSC_FSCTL_OPERATION_PRINCIPAL_ID_TO_SID"
0x1400625b0  retn
0x1400625b2  lea     rax, aCscFsctlOperat_3; "CSC_FSCTL_OPERATION_SET_LOCATION_DATABA"...
0x1400625b9  retn
0x1400625bb  lea     rax, aCscFsctlOperat_20; "CSC_FSCTL_OPERATION_QUERY_LOCATION_DATA"...
0x1400625c2  retn
0x1400625c4  lea     rax, aCscFsctlOperat_51; "CSC_FSCTL_OPERATION_SET_DATABASE_EVICTI"...
0x1400625cb  retn
0x1400625cd  lea     rax, aCscFsctlOperat_39; "CSC_FSCTL_OPERATION_UPCALL_RECEIVE"
0x1400625d4  retn
0x1400625d6  mov     edx, ecx
0x1400625d8  sub     edx, 1Eh
0x1400625db  jz      short loc_140062643
0x1400625dd  sub     edx, 1
0x1400625e0  jz      short loc_14006263A
0x1400625e2  sub     edx, 1
0x1400625e5  jz      short loc_140062631
0x1400625e7  sub     edx, 1
0x1400625ea  jz      short loc_140062628
0x1400625ec  sub     edx, 1
0x1400625ef  jz      short loc_14006261F
0x1400625f1  sub     edx, 1
0x1400625f4  jz      short loc_140062616
0x1400625f6  sub     edx, 1
0x1400625f9  jz      short loc_14006260D
0x1400625fb  cmp     edx, 1
0x1400625fe  jnz     loc_140062845
0x140062604  lea     rax, aCscFsctlOperat_0; "CSC_FSCTL_OPERATION_ADD_SID"
0x14006260b  retn
0x14006260d  lea     rax, aCscFsctlOperat_32; "CSC_FSCTL_OPERATION_GET_SID_INDEX"
0x140062614  retn
0x140062616  lea     rax, aCscFsctlOperat_50; "CSC_FSCTL_OPERATION_EXTRACT_QUERY_ITEM_"...
0x14006261d  retn
0x14006261f  lea     rax, aCscFsctlOperat_47; "CSC_FSCTL_OPERATION_EXTRACT_DIR"
0x140062626  retn
0x140062628  lea     rax, aCscFsctlOperat_67; "CSC_FSCTL_OPERATION_ENCRYPT_DECRYPT"
0x14006262f  retn
0x140062631  lea     rax, aCscFsctlOperat_44; "CSC_FSCTL_OPERATION_HAS_CREDENTIAL_ERRO"...
0x140062638  retn
0x14006263a  lea     rax, aCscFsctlOperat_9; "CSC_FSCTL_OPERATION_DELETE_CREDENTIAL"
0x140062641  retn
0x140062643  lea     rax, aCscFsctlOperat_52; "CSC_FSCTL_OPERATION_UPCALL_REPLY"
0x14006264a  retn
0x14006264c  lea     rax, aCscFsctlOperat_42; "CSC_FSCTL_OPERATION_IMPORT_START"
0x140062653  retn
0x140062655  cmp     ecx, 39h ; '9'
0x140062658  jg      loc_14006277F
0x14006265e  jz      loc_140062776
0x140062664  cmp     ecx, 30h ; '0'
0x140062667  jg      loc_140062700
0x14006266d  jz      loc_1400626F7
0x140062673  mov     edx, ecx
0x140062675  sub     edx, 27h ; '''
0x140062678  jz      short loc_1400626EE
0x14006267a  sub     edx, 1
0x14006267d  jz      short loc_1400626E5
0x14006267f  sub     edx, 1
0x140062682  jz      short loc_1400626DC
0x140062684  sub     edx, 1
0x140062687  jz      short loc_1400626D3
0x140062689  sub     edx, 1
0x14006268c  jz      short loc_1400626CA
0x14006268e  sub     edx, 1
0x140062691  jz      short loc_1400626C1
0x140062693  sub     edx, 1
0x140062696  jz      short loc_1400626B8
0x140062698  sub     edx, 1
0x14006269b  jz      short loc_1400626AF
0x14006269d  cmp     edx, 1
0x1400626a0  jnz     loc_140062845
0x1400626a6  lea     rax, aCscFsctlOperat_71; "CSC_FSCTL_OPERATION_CONTROL_FAULT_INJEC"...
0x1400626ad  retn
0x1400626af  lea     rax, aCscFsctlOperat_24; "CSC_FSCTL_OPERATION_UPDATE_SUSPENDED_IT"...
0x1400626b6  retn
0x1400626b8  lea     rax, aCscFsctlOperat_4; "CSC_FSCTL_OPERATION_CREATE_REPLACE_DATA"...
0x1400626bf  retn
0x1400626c1  lea     rax, aCscFsctlOperat_28; "CSC_FSCTL_OPERATION_IMPORT_QUERY_GATHER"...
0x1400626c8  retn
0x1400626ca  lea     rax, aCscFsctlOperat_65; "CSC_FSCTL_OPERATION_IMPORT_QUERY_TEMP_N"...
0x1400626d1  retn
0x1400626d3  lea     rax, aCscFsctlOperat_15; "CSC_FSCTL_OPERATION_IMPORT_FILE"
0x1400626da  retn
0x1400626dc  lea     rax, aCscFsctlOperat_23; "CSC_FSCTL_OPERATION_IMPORT_ITEM"
0x1400626e3  retn
0x1400626e5  lea     rax, aCscFsctlOperat_63; "CSC_FSCTL_OPERATION_IMPORT_END"
0x1400626ec  retn
0x1400626ee  lea     rax, aCscFsctlOperat_38; "CSC_FSCTL_OPERATION_IMPORT_ASSOCIATE_HA"...
0x1400626f5  retn
0x1400626f7  lea     rax, aCscFsctlOperat_46; "CSC_FSCTL_OPERATION_SET_CONNECTION_PERF"
0x1400626fe  retn
0x140062700  mov     edx, ecx
0x140062702  sub     edx, 31h ; '1'
0x140062705  jz      short loc_14006276D
0x140062707  sub     edx, 1
0x14006270a  jz      short loc_140062764
0x14006270c  sub     edx, 1
0x14006270f  jz      short loc_14006275B
0x140062711  sub     edx, 1
0x140062714  jz      short loc_140062752
0x140062716  sub     edx, 1
0x140062719  jz      short loc_140062749
0x14006271b  sub     edx, 1
0x14006271e  jz      short loc_140062740
0x140062720  sub     edx, 1
0x140062723  jz      short loc_140062737
0x140062725  cmp     edx, 1
0x140062728  jnz     loc_140062845
0x14006272e  lea     rax, aCscFsctlOperat_40; "CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_R"...
0x140062735  retn
0x140062737  lea     rax, aCscFsctlOperat_49; "CSC_FSCTL_OPERATION_OFFLINE_DIRECTORY_R"...
0x14006273e  retn
0x140062740  lea     rax, aCscFsctlOperat_61; "CSC_FSCTL_OPERATION_KNOWN_OFFLINE_PATH"
0x140062747  retn
0x140062749  lea     rax, aCscFsctlOperat_66; "CSC_FSCTL_OPERATION_TEST"
0x140062750  retn
0x140062752  lea     rax, aCscFsctlOperat_54; "CSC_FSCTL_OPERATION_REBOOT_RENAME_ADD"
0x140062759  retn
0x14006275b  lea     rax, aCscFsctlOperat_1; "CSC_FSCTL_OPERATION_REPLACE_SID"
0x140062762  retn
0x140062764  lea     rax, aCscFsctlOperat_48; "CSC_FSCTL_OPERATION_FLUSH_PRIORITY_QUEU"...
0x14006276b  retn
0x14006276d  lea     rax, aCscFsctlOperat_60; "CSC_FSCTL_OPERATION_SET_SPARSE_EXCLUSIO"...
0x140062774  retn
0x140062776  lea     rax, aCscFsctlOperat_31; "CSC_FSCTL_OPERATION_CONVERT_BACKOUT_HAN"...
0x14006277d  retn
0x14006277f  cmp     ecx, 43h ; 'C'
0x140062782  jg      loc_14006281B
0x140062788  jz      loc_140062812
0x14006278e  mov     edx, ecx
0x140062790  sub     edx, 3Ah ; ':'
0x140062793  jz      short loc_140062809
0x140062795  sub     edx, 1
0x140062798  jz      short loc_140062800
0x14006279a  sub     edx, 1
0x14006279d  jz      short loc_1400627F7
0x14006279f  sub     edx, 1
0x1400627a2  jz      short loc_1400627EE
0x1400627a4  sub     edx, 1
0x1400627a7  jz      short loc_1400627E5
0x1400627a9  sub     edx, 1
0x1400627ac  jz      short loc_1400627DC
0x1400627ae  sub     edx, 1
0x1400627b1  jz      short loc_1400627D3
0x1400627b3  sub     edx, 1
0x1400627b6  jz      short loc_1400627CA
0x1400627b8  cmp     edx, 1
0x1400627bb  jnz     loc_140062845
0x1400627c1  lea     rax, aCscFsctlOperat_55; "CSC_FSCTL_OPERATION_CLEAR_CONNECTION_PE"...
0x1400627c8  retn
0x1400627ca  lea     rax, aCscFsctlOperat_64; "CSC_FSCTL_OPERATION_SET_PREFETCH"
0x1400627d1  retn
0x1400627d3  lea     rax, aCscFsctlOperat_56; "CSC_FSCTL_OPERATION_RETRIEVE_HASH_DATA"
0x1400627da  retn
0x1400627dc  lea     rax, aCscFsctlOperat_68; "CSC_FSCTL_OPERATION_WRITE_STORE_DATA"
0x1400627e3  retn
0x1400627e5  lea     rax, aCscFsctlOperat_13; "CSC_FSCTL_OPERATION_QUERY_PERFCOUNTERS"
0x1400627ec  retn
0x1400627ee  lea     rax, aCscFsctlOperat_29; "CSC_FSCTL_OPERATION_SET_PEER_CACHING_EN"...
0x1400627f5  retn
0x1400627f7  lea     rax, aCscFsctlOperat_16; "CSC_FSCTL_OPERATION_SET_TRANSPARENT_CAC"...
0x1400627fe  retn
0x140062800  lea     rax, aCscFsctlOperat_43; "CSC_FSCTL_OPERATION_SET_EXCLUDED_FILE_T"...
0x140062807  retn
0x140062809  lea     rax, aCscFsctlOperat_6; "CSC_FSCTL_OPERATION_QUERY_CLIENT_OPLOCK"...
0x140062810  retn
0x140062812  lea     rax, aCscFsctlOperat_21; "CSC_FSCTL_OPERATION_GET_CONNECTION_PERF"
0x140062819  retn
0x14006281b  mov     edx, ecx
0x14006281d  sub     edx, 44h ; 'D'
0x140062820  jz      short loc_14006289B
0x140062822  sub     edx, 1
0x140062825  jz      short loc_140062892
0x140062827  sub     edx, 1
0x14006282a  jz      short loc_140062889
0x14006282c  sub     edx, 1
0x14006282f  jz      short loc_140062880
0x140062831  sub     edx, 1
0x140062834  jz      short loc_140062877
0x140062836  sub     edx, 1
0x140062839  jz      short loc_14006286E
0x14006283b  sub     edx, 1
  ... truncated ...
```
