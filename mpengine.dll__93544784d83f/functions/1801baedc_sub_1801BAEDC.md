# sub_1801BAEDC

- ea: `0x1801baedc`
- end: `0x1801bb83e`
- name: `sub_1801BAEDC`
- size: `2402`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `44`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801c3284`
- `0x1801ccb70`
- `0x1801d2a68`
- `0x1801d3788`
- `0x1803dfe34`
- `0x1804d23c0`
- `0x1804d3018`
- `0x1804d9270`
- `0x1804d9bac`
- `0x1804e600c`
- `0x1804e759c`
- `0x1804e7d88`
- `0x1804e8604`
- `0x1804f2ad0`
- `0x1804f3334`
- `0x1804f3b98`
- `0x1804f441c`
- `0x1804f90bc`
- `0x1804f9880`
- `0x1804ff2d4`
- `0x18050c1a8`
- `0x18050fe40`
- `0x180510560`
- `0x18072c278`
- `0x18072cb0c`
- `0x18072d1a8`
- `0x18072d9bc`
- `0x18072e250`
- `0x18072ea50`
- `0x18073bbd0`
- `0x18073c46c`
- `0x18073cccc`
- `0x18073d568`
- `0x18073ddcc`
- `0x18073e62c`
- `0x180871044`
- `0x1808719c0`
- `0x1809a1ed0`
- `0x180a24b30`
- `0x180a26f10`
- `0x180a294b8`
- `0x180a29cf8`
- `0x180a2d8b0`
- `0x180a2e144`

## callees

- `0x1801baedc`

## string_xrefs

- `0x1801bb131`: `SIGNATURE_TYPE_FILEPATH`
- `0x1801bb197`: `SIGNATURE_TYPE_ASEP_FILEPATH`
- `0x1801bb1d7`: `SIGNATURE_TYPE_VDLL_X86`
- `0x1801bb268`: `SIGNATURE_TYPE_VDLL_X64`
- `0x1801bb33f`: `SIGNATURE_TYPE_VDLL_ARM`
- `0x1801bb303`: `SIGNATURE_TYPE_VDLL_ARM64`
- `0x1801bb5c1`: `SIGNATURE_TYPE_VDLL_MSIL`
- `0x1801bb387`: `SIGNATURE_TYPE_THREAD_X86`
- `0x1801bb413`: `SIGNATURE_TYPE_THREAD_X64`
- `0x1801bb40b`: `SIGNATURE_TYPE_THREAD_ARM64`
- `0x1801bb54d`: `SIGNATURE_TYPE_THREAD_ARM`
- `0x1801bb44e`: `SIGNATURE_TYPE_VDLL_SYMINFO`
- `0x1801bb4d2`: `SIGNATURE_TYPE_FASTPATH_DATA`
- `0x1801bb4ca`: `SIGNATURE_TYPE_FASTPATH_SDN`
- `0x1801bb6eb`: `SIGNATURE_TYPE_FASTPATH_TDN`
- `0x1801bb6db`: `SIGNATURE_TYPE_FASTPATH_SDN_EX`
- `0x1801bb4aa`: `SIGNATURE_TYPE_COMMON_CODE`
- `0x1801bb55d`: `SIGNATURE_TYPE_VDLL_META`
- `0x1801bb78e`: `SIGNATURE_TYPE_VDLL_META_X64`
- `0x1801bb786`: `SIGNATURE_TYPE_VDLL_META_ARM`
- `0x1801bb77e`: `SIGNATURE_TYPE_VDLL_META_MSIL`
- `0x1801bb53d`: `SIGNATURE_TYPE_MSILFOP`
- `0x1801bb5d1`: `SIGNATURE_TYPE_VDLL_CHECKSUM`
- `0x1801bb5c9`: `SIGNATURE_TYPE_THREAT_UPDATE_STATUS`
- `0x1801bb5b1`: `SIGNATURE_TYPE_MSILFOPEX`

## pseudocode

```c
const char *__fastcall sub_1801BAEDC(unsigned __int8 a1)
{
  if ( a1 <= 0x9Du )
  {
    if ( a1 == 157 )
      return "SIGNATURE_TYPE_THREAD_X86";
    if ( a1 > 0x6Bu )
    {
      if ( a1 > 0x87u )
      {
        if ( a1 > 0x91u )
        {
          switch ( a1 )
          {
            case 0x92u:
              return "SIGNATURE_TYPE_ASCRIPTHSTR_EXT";
            case 0x95u:
              return "SIGNATURE_TYPE_PEBMPAT";
            case 0x96u:
              return "SIGNATURE_TYPE_AAGGREGATOR";
            case 0x97u:
              return "SIGNATURE_TYPE_SAMPLE_REQUEST_BY_NAME";
            case 0x98u:
              return "SIGNATURE_TYPE_REMOVAL_POLICY_BY_NAME";
            case 0x99u:
              return "SIGNATURE_TYPE_TUNNEL_X86";
            case 0x9Au:
              return "SIGNATURE_TYPE_TUNNEL_X64";
            case 0x9Bu:
              return "SIGNATURE_TYPE_TUNNEL_ARM64";
            case 0x9Cu:
              return "SIGNATURE_TYPE_VDLL_ARM";
          }
        }
        else
        {
          switch ( a1 )
          {
            case 0x91u:
              return "SIGNATURE_TYPE_VDLL_ARM64";
            case 0x88u:
              return "SIGNATURE_TYPE_UFSP_DISABLE";
            case 0x89u:
              return "SIGNATURE_TYPE_FOPEX";
            case 0x8Au:
              return "SIGNATURE_TYPE_PEPCODE";
            case 0x8Bu:
              return "SIGNATURE_TYPE_IL_PATTERN";
            case 0x8Cu:
              return "SIGNATURE_TYPE_ELFHSTR_EXT";
            case 0x8Du:
              return "SIGNATURE_TYPE_MACHOHSTR_EXT";
            case 0x8Eu:
              return "SIGNATURE_TYPE_DOSHSTR_EXT";
            case 0x8Fu:
              return "SIGNATURE_TYPE_MACROHSTR_EXT";
            case 0x90u:
              return "SIGNATURE_TYPE_TARGET_SCRIPT_PCODE";
          }
        }
      }
      else
      {
        if ( a1 == 135 )
          return "SIGNATURE_TYPE_PESTATIC";
        if ( a1 > 0x7Bu )
        {
          switch ( a1 )
          {
            case 0x7Cu:
              return "SIGNATURE_TYPE_VDLL_X64";
            case 0x7Eu:
              return "SIGNATURE_TYPE_SNID";
            case 0x7Fu:
              return "SIGNATURE_TYPE_FOP";
            case 0x80u:
              return "SIGNATURE_TYPE_KCRCE";
            case 0x81u:
              return "SIGNATURE_TYPE_DELTA_BLOB_ZSTD";
            case 0x83u:
              return "SIGNATURE_TYPE_VFILE";
            case 0x84u:
              return "SIGNATURE_TYPE_SIGFLAGS";
            case 0x85u:
              return "SIGNATURE_TYPE_PEHSTR_EXT2";
            case 0x86u:
              return "SIGNATURE_TYPE_PEMAIN_LOCATOR";
          }
        }
        else
        {
          if ( a1 == 123 )
            return "SIGNATURE_TYPE_SAMPLE_REQUEST";
          if ( a1 > 0x75u )
          {
            switch ( a1 )
            {
              case 'w':
                return "SIGNATURE_TYPE_PATTMATCH_V2";
              case 'x':
                return "SIGNATURE_TYPE_PEHSTR_EXT";
              case 'y':
                return "SIGNATURE_TYPE_VDLL_X86";
              case 'z':
                return "SIGNATURE_TYPE_VERSIONCHECK";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 'u':
                return "SIGNATURE_TYPE_ASEP_FOLDERNAME";
              case 'l':
                return "SIGNATURE_TYPE_REVOKED_CERTIFICATE";
              case 'p':
                return "SIGNATURE_TYPE_TRUSTED_PUBLISHER";
              case 'q':
                return "SIGNATURE_TYPE_ASEP_FILEPATH";
              case 's':
                return "SIGNATURE_TYPE_DELTA_BLOB";
              case 't':
                return "SIGNATURE_TYPE_DELTA_BLOB_RECINFO";
            }
          }
        }
      }
    }
    else
    {
      if ( a1 == 107 )
        return "SIGNATURE_TYPE_WVT_EXCEPTION";
      if ( a1 > 0x50u )
      {
        if ( a1 > 0x5Eu )
        {
          switch ( a1 )
          {
            case '_':
              return "SIGNATURE_TYPE_FILEPATH";
            case '`':
              return "SIGNATURE_TYPE_FOLDERNAME";
            case 'a':
              return "SIGNATURE_TYPE_PEHSTR";
            case 'b':
              return "SIGNATURE_TYPE_LOCALHASH";
            case 'c':
              return "SIGNATURE_TYPE_REGKEY";
            case 'd':
              return "SIGNATURE_TYPE_HOSTSENTRY";
            case 'g':
              return "SIGNATURE_TYPE_STATIC";
            case 'i':
              return "SIGNATURE_TYPE_LATENT_THREAT";
            case 'j':
              return "SIGNATURE_TYPE_REMOVAL_POLICY";
          }
        }
        else
        {
          switch ( a1 )
          {
            case '^':
              return "SIGNATURE_TYPE_FILENAME";
            case 'Q':
              return "SIGNATURE_TYPE_PATTMATCH";
            case 'S':
              return "SIGNATURE_TYPE_RPFROUTINE";
            case 'U':
              return "SIGNATURE_TYPE_NID";
            case 'V':
              return "SIGNATURE_TYPE_GENSFX";
            case 'W':
              return "SIGNATURE_TYPE_UNPLIB";
            case 'X':
              return "SIGNATURE_TYPE_DEFAULTS";
            case '[':
              return "SIGNATURE_TYPE_DBVAR";
            case '\\':
              return "SIGNATURE_TYPE_THREAT_BEGIN";
            case ']':
              return "SIGNATURE_TYPE_THREAT_END";
          }
        }
      }
      else
      {
        if ( a1 == 80 )
          return "SIGNATURE_TYPE_CKSIMPLEREC";
        if ( a1 > 0x30u )
        {
          switch ( a1 )
          {
            case '=':
              return "SIGNATURE_TYPE_PEFILE_CURE";
            case '>':
              return "SIGNATURE_TYPE_MAC_CURE";
            case '@':
              return "SIGNATURE_TYPE_SIGTREE";
            case 'A':
              return "SIGNATURE_TYPE_SIGTREE_EXT";
            case 'B':
              return "SIGNATURE_TYPE_MACRO_PCODE";
            case 'C':
              return "SIGNATURE_TYPE_MACRO_SOURCE";
            case 'D':
              return "SIGNATURE_TYPE_BOOT";
            case 'I':
              return "SIGNATURE_TYPE_CLEANSCRIPT";
            case 'J':
              return "SIGNATURE_TYPE_TARGET_SCRIPT";
          }
        }
        else
        {
          if ( a1 == 48 )
            return "SIGNATURE_TYPE_TITANFLT";
          if ( a1 > 0x21u )
          {
            switch ( a1 )
            {
              case '\'':
                return "SIGNATURE_TYPE_NSCRIPT_NORMAL";
              case '(':
                return "SIGNATURE_TYPE_NSCRIPT_SP";
              case ')':
                return "SIGNATURE_TYPE_NSCRIPT_BRUTE";
              case ',':
                return "SIGNATURE_TYPE_NSCRIPT_CURE";
            }
          }
          else
          {
            switch ( a1 )
            {
              case 0x21u:
                return "SIGNATURE_TYPE_POLYVIR32";
              case 1u:
                return "SIGNATURE_TYPE_RESERVED";
              case 2u:
                return "SIGNATURE_TYPE_VOLATILE_THREAT_INFO";
              case 3u:
                return "SIGNATURE_TYPE_VOLATILE_THREAT_ID";
              case 0x11u:
                return "SIGNATURE_TYPE_CKOLDREC";
              case 0x20u:
                return "SIGNATURE_TYPE_KVIR32";
            }
          }
        }
      }
    }
    return "SIGNATURE_TYPE_UNKNOWN";
  }
  if ( a1 <= 0xC7u )
  {
    if ( a1 == 199 )
      return "SIGNATURE_TYPE_VBFOPEX";
    if ( a1 > 0xB2u )
    {
      if ( a1 > 0xBDu )
      {
        switch ( a1 )
        {
          case 0xBEu:
            return "SIGNATURE_TYPE_DEXHSTR_EXT";
          case 0xBFu:
            return "SIGNATURE_TYPE_JAVAHSTR_EXT";
          case 0xC0u:
            return "SIGNATURE_TYPE_MAGICCODE";
          case 0xC1u:
            return "SIGNATURE_TYPE_CLEANSTORE_RULE";
          case 0xC2u:
            return "SIGNATURE_TYPE_VDLL_CHECKSUM";
          case 0xC3u:
            return "SIGNATURE_TYPE_THREAT_UPDATE_STATUS";
          case 0xC4u:
            return "SIGNATURE_TYPE_VDLL_MSIL";
          case 0xC5u:
            return "SIGNATURE_TYPE_ARHSTR_EXT";
          case 0xC6u:
            return "SIGNATURE_TYPE_MSILFOPEX";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0xBDu:
            return "SIGNATURE_TYPE_LUASTANDALONE";
          case 0xB3u:
            return "SIGNATURE_TYPE_SIGTREE_BM";
          case 0xB4u:
            return "SIGNATURE_TYPE_VBFOP";
          case 0xB5u:
            return "SIGNATURE_TYPE_VDLL_META";
          case 0xB6u:
            return "SIGNATURE_TYPE_TUNNEL_ARM";
          case 0xB7u:
            return "SIGNATURE_TYPE_THREAD_ARM";
          case 0xB8u:
            return "SIGNATURE_TYPE_PCODEVALIDATOR";
          case 0xBAu:
            return "SIGNATURE_TYPE_MSILFOP";
          case 0xBBu:
            return "SIGNATURE_TYPE_KPAT";
          case 0xBCu:
            return "SIGNATURE_TYPE_KPATEX";
        }
      }
    }
    else
    {
      if ( a1 == 178 )
        return "SIGNATURE_TYPE_VFILEEX";
      if ( a1 > 0xA8u )
      {
        switch ( a1 )
        {
          case 0xA9u:
            return "SIGNATURE_TYPE_NDAT";
          case 0xAAu:
            return "SIGNATURE_TYPE_FASTPATH_DATA";
          case 0xABu:
            return "SIGNATURE_TYPE_FASTPATH_SDN";
          case 0xACu:
            return "SIGNATURE_TYPE_DATABASE_CERT";
          case 0xADu:
            return "SIGNATURE_TYPE_SOURCE_INFO";
          case 0xAEu:
            return "SIGNATURE_TYPE_HIDDEN_FILE";
          case 0xAFu:
            return "SIGNATURE_TYPE_COMMON_CODE";
          case 0xB0u:
            return "SIGNATURE_TYPE_VREG";
          case 0xB1u:
            return "SIGNATURE_TYPE_NISBLOB";
        }
      }
      else
      {
        if ( a1 == 168 )
          return "SIGNATURE_TYPE_BM_INFO";
        if ( a1 > 0xA3u )
        {
          switch ( a1 )
          {
            case 0xA4u:
              return "SIGNATURE_TYPE_VSTORE";
            case 0xA5u:
              return "SIGNATURE_TYPE_VDLL_SYMINFO";
            case 0xA6u:
              return "SIGNATURE_TYPE_IL2_PATTERN";
            case 0xA7u:
              return "SIGNATURE_TYPE_BM_STATIC";
          }
        }
        else
        {
          switch ( a1 )
          {
            case 0xA3u:
              return "SIGNATURE_TYPE_VDM_METADATA";
            case 0x9Eu:
              return "SIGNATURE_TYPE_THREAD_X64";
            case 0x9Fu:
              return "SIGNATURE_TYPE_THREAD_ARM64";
            case 0xA0u:
              return "SIGNATURE_TYPE_FRIENDLYFILE_SHA256";
            case 0xA1u:
              return "SIGNATURE_TYPE_FRIENDLYFILE_SHA512";
            case 0xA2u:
              return "SIGNATURE_TYPE_SHARED_THREAT";
          }
        }
      }
    }
    return "SIGNATURE_TYPE_UNKNOWN";
  }
  if ( a1 <= 0xDBu )
  {
    if ( a1 == 219 )
      return "SIGNATURE_TYPE_BLOOM_FILTER";
    if ( a1 > 0xD1u )
    {
      switch ( a1 )
      {
        case 0xD2u:
          return "SIGNATURE_TYPE_REWSIGS";
        case 0xD3u:
          return "SIGNATURE_TYPE_AUTOITHSTR_EXT";
        case 0xD4u:
          return "SIGNATURE_TYPE_INNOHSTR_EXT";
        case 0xD5u:
          return "SIGNATURE_TYPE_CERT_STORE_ENTRY";
        case 0xD6u:
          return "SIGNATURE_TYPE_EXPLICITRESOURCE";
        case 0xD7u:
          return "SIGNATURE_TYPE_CMDHSTR_EXT";
        case 0xD8u:
          return "SIGNATURE_TYPE_FASTPATH_TDN";
        case 0xD9u:
          return "SIGNATURE_TYPE_EXPLICITRESOURCEHASH";
        case 0xDAu:
          return "SIGNATURE_TYPE_FASTPATH_SDN_EX";
      }
    }
    else
    {
      switch ( a1 )
      {
        case 0xD1u:
          return "SIGNATURE_TYPE_SWFHSTR_EXT";
        case 0xC8u:
          return "SIGNATURE_TYPE_FOP64";
        case 0xC9u:
          return "SIGNATURE_TYPE_FOPEX64";
        case 0xCAu:
          return "SIGNATURE_TYPE_JSINIT";
        case 0xCBu:
          return "SIGNATURE_TYPE_PESTATICEX";
        case 0xCCu:
          return "SIGNATURE_TYPE_KCRCEX";
        case 0xCDu:
          return "SIGNATURE_TYPE_FTRIE_POS";
        case 0xCEu:
          return "SIGNATURE_TYPE_NID64";
        case 0xCFu:
          return "SIGNATURE_TYPE_MACRO_PCODE64";
        case 0xD0u:
          return "SIGNATURE_TYPE_BRUTE";
      }
    }
    return "SIGNATURE_TYPE_UNKNOWN";
  }
  if ( a1 <= 0xE6u )
  {
    switch ( a1 )
    {
      case 0xE6u:
        return "SIGNATURE_TYPE_SNIDEX2";
      case 0xDCu:
        return "SIGNATURE_TYPE_RESEARCH_TAG";
      case 0xDEu:
        return "SIGNATURE_TYPE_ENVELOPE";
      case 0xDFu:
        return "SIGNATURE_TYPE_REMOVAL_POLICY64";
      case 0xE0u:
        return "SIGNATURE_TYPE_REMOVAL_POLICY64_BY_NAME";
      case 0xE1u:
        return "SIGNATURE_TYPE_VDLL_META_X64";
      case 0xE2u:
        return "SIGNATURE_TYPE_VDLL_META_ARM";
      case 0xE3u:
        return "SIGNATURE_TYPE_VDLL_META_MSIL";
      case 0xE4u:
        return "SIGNATURE_TYPE_MDBHSTR_EXT";
      case 0xE5u:
        return "SIGNATURE_TYPE_SNIDEX";
    }
    return "SIGNATURE_TYPE_UNKNOWN";
  }
  switch ( a1 )
  {
    case 0xE7u:
      return "SIGNATURE_TYPE_AAGGREGATOREX";
    case 0xE8u:
      return "SIGNATURE_TYPE_PUA_APPMAP";
    case 0xE9u:
      return "SIGNATURE_TYPE_PROPERTY_BAG";
    case 0xEAu:
      return "SIGNATURE_TYPE_DMGHSTR_EXT";
    case 0xEBu:
      return "SIGNATURE_TYPE_DATABASE_CATALOG";
    case 0xECu:
      return "SIGNATURE_TYPE_DATABASE_CERT2";
    case 0xEDu:
      return "SIGNATURE_TYPE_BM_ENV_VAR_MAP";
    case 0xEEu:
      return "SIGNATURE_TYPE_DATABASE_CERT3";
  }
  if ( a1 != 239 )
    return "SIGNATURE_TYPE_UNKNOWN";
  return "SIGNATURE_TYPE_ARHSTR_POSIX_EXT";
}

```

## disassembly

```asm
0x1801baedc  movzx   edx, cl
0x1801baedf  mov     eax, 9Dh
0x1801baee4  cmp     edx, eax
0x1801baee6  ja      loc_1801BB38F
0x1801baeec  jz      loc_1801BB387
0x1801baef2  cmp     edx, 6Bh ; 'k'
0x1801baef5  ja      loc_1801BB141
0x1801baefb  jz      loc_1801BB139
0x1801baf01  cmp     edx, 50h ; 'P'
0x1801baf04  ja      loc_1801BB034
0x1801baf0a  jz      loc_1801BB02C
0x1801baf10  cmp     edx, 30h ; '0'
0x1801baf13  ja      loc_1801BAFB3
0x1801baf19  jz      loc_1801BAFAB
0x1801baf1f  cmp     edx, 21h ; '!'
0x1801baf22  ja      short loc_1801BAF73
0x1801baf24  jz      short loc_1801BAF6B
0x1801baf26  sub     edx, 1
0x1801baf29  jz      short loc_1801BAF63
0x1801baf2b  sub     edx, 1
0x1801baf2e  jz      short loc_1801BAF5B
0x1801baf30  sub     edx, 1
0x1801baf33  jz      short loc_1801BAF53
0x1801baf35  sub     edx, 0Eh
0x1801baf38  jz      short loc_1801BAF4B
0x1801baf3a  cmp     edx, 0Fh
0x1801baf3d  jnz     loc_1801BB7EE
0x1801baf43  lea     rax, aSignatureTypeK; "SIGNATURE_TYPE_KVIR32"
0x1801baf4a  retn
0x1801baf4b  lea     rax, aSignatureTypeC; "SIGNATURE_TYPE_CKOLDREC"
0x1801baf52  retn
0x1801baf53  lea     rax, aSignatureTypeV; "SIGNATURE_TYPE_VOLATILE_THREAT_ID"
0x1801baf5a  retn
0x1801baf5b  lea     rax, aSignatureTypeV_0; "SIGNATURE_TYPE_VOLATILE_THREAT_INFO"
0x1801baf62  retn
0x1801baf63  lea     rax, aSignatureTypeR; "SIGNATURE_TYPE_RESERVED"
0x1801baf6a  retn
0x1801baf6b  lea     rax, aSignatureTypeP; "SIGNATURE_TYPE_POLYVIR32"
0x1801baf72  retn
0x1801baf73  sub     edx, 27h ; '''
0x1801baf76  jz      short loc_1801BAFA3
0x1801baf78  sub     edx, 1
0x1801baf7b  jz      short loc_1801BAF9B
0x1801baf7d  sub     edx, 1
0x1801baf80  jz      short loc_1801BAF93
0x1801baf82  cmp     edx, 3
0x1801baf85  jnz     loc_1801BB7EE
0x1801baf8b  lea     rax, aSignatureTypeN; "SIGNATURE_TYPE_NSCRIPT_CURE"
0x1801baf92  retn
0x1801baf93  lea     rax, aSignatureTypeN_0; "SIGNATURE_TYPE_NSCRIPT_BRUTE"
0x1801baf9a  retn
0x1801baf9b  lea     rax, aSignatureTypeN_1; "SIGNATURE_TYPE_NSCRIPT_SP"
0x1801bafa2  retn
0x1801bafa3  lea     rax, aSignatureTypeN_2; "SIGNATURE_TYPE_NSCRIPT_NORMAL"
0x1801bafaa  retn
0x1801bafab  lea     rax, aSignatureTypeT; "SIGNATURE_TYPE_TITANFLT"
0x1801bafb2  retn
0x1801bafb3  sub     edx, 3Dh ; '='
0x1801bafb6  jz      short loc_1801BB024
0x1801bafb8  sub     edx, 1
0x1801bafbb  jz      short loc_1801BB01C
0x1801bafbd  sub     edx, 2
0x1801bafc0  jz      short loc_1801BB014
0x1801bafc2  sub     edx, 1
0x1801bafc5  jz      short loc_1801BB00C
0x1801bafc7  sub     edx, 1
0x1801bafca  jz      short loc_1801BB004
0x1801bafcc  sub     edx, 1
0x1801bafcf  jz      short loc_1801BAFFC
0x1801bafd1  sub     edx, 1
0x1801bafd4  jz      short loc_1801BAFF4
0x1801bafd6  sub     edx, 5
0x1801bafd9  jz      short loc_1801BAFEC
0x1801bafdb  cmp     edx, 1
0x1801bafde  jnz     loc_1801BB7EE
0x1801bafe4  lea     rax, aSignatureTypeT_0; "SIGNATURE_TYPE_TARGET_SCRIPT"
0x1801bafeb  retn
0x1801bafec  lea     rax, aSignatureTypeC_0; "SIGNATURE_TYPE_CLEANSCRIPT"
0x1801baff3  retn
0x1801baff4  lea     rax, aSignatureTypeB; "SIGNATURE_TYPE_BOOT"
0x1801baffb  retn
0x1801baffc  lea     rax, aSignatureTypeM; "SIGNATURE_TYPE_MACRO_SOURCE"
0x1801bb003  retn
0x1801bb004  lea     rax, aSignatureTypeM_0; "SIGNATURE_TYPE_MACRO_PCODE"
0x1801bb00b  retn
0x1801bb00c  lea     rax, aSignatureTypeS; "SIGNATURE_TYPE_SIGTREE_EXT"
0x1801bb013  retn
0x1801bb014  lea     rax, aSignatureTypeS_0; "SIGNATURE_TYPE_SIGTREE"
0x1801bb01b  retn
0x1801bb01c  lea     rax, aSignatureTypeM_1; "SIGNATURE_TYPE_MAC_CURE"
0x1801bb023  retn
0x1801bb024  lea     rax, aSignatureTypeP_0; "SIGNATURE_TYPE_PEFILE_CURE"
0x1801bb02b  retn
0x1801bb02c  lea     rax, aSignatureTypeC_1; "SIGNATURE_TYPE_CKSIMPLEREC"
0x1801bb033  retn
0x1801bb034  cmp     edx, 5Eh ; '^'
0x1801bb037  ja      loc_1801BB0C0
0x1801bb03d  jz      short loc_1801BB0B8
0x1801bb03f  sub     edx, 51h ; 'Q'
0x1801bb042  jz      short loc_1801BB0B0
0x1801bb044  sub     edx, 2
0x1801bb047  jz      short loc_1801BB0A8
0x1801bb049  sub     edx, 2
0x1801bb04c  jz      short loc_1801BB0A0
0x1801bb04e  sub     edx, 1
0x1801bb051  jz      short loc_1801BB098
0x1801bb053  sub     edx, 1
0x1801bb056  jz      short loc_1801BB090
0x1801bb058  sub     edx, 1
0x1801bb05b  jz      short loc_1801BB088
0x1801bb05d  sub     edx, 3
0x1801bb060  jz      short loc_1801BB080
0x1801bb062  sub     edx, 1
0x1801bb065  jz      short loc_1801BB078
0x1801bb067  cmp     edx, 1
0x1801bb06a  jnz     loc_1801BB7EE
0x1801bb070  lea     rax, aSignatureTypeT_1; "SIGNATURE_TYPE_THREAT_END"
0x1801bb077  retn
0x1801bb078  lea     rax, aSignatureTypeT_2; "SIGNATURE_TYPE_THREAT_BEGIN"
0x1801bb07f  retn
0x1801bb080  lea     rax, aSignatureTypeD; "SIGNATURE_TYPE_DBVAR"
0x1801bb087  retn
0x1801bb088  lea     rax, aSignatureTypeD_0; "SIGNATURE_TYPE_DEFAULTS"
0x1801bb08f  retn
0x1801bb090  lea     rax, aSignatureTypeU; "SIGNATURE_TYPE_UNPLIB"
0x1801bb097  retn
0x1801bb098  lea     rax, aSignatureTypeG; "SIGNATURE_TYPE_GENSFX"
0x1801bb09f  retn
0x1801bb0a0  lea     rax, aSignatureTypeN_3; "SIGNATURE_TYPE_NID"
0x1801bb0a7  retn
0x1801bb0a8  lea     rax, aSignatureTypeR_0; "SIGNATURE_TYPE_RPFROUTINE"
0x1801bb0af  retn
0x1801bb0b0  lea     rax, aSignatureTypeP_1; "SIGNATURE_TYPE_PATTMATCH"
0x1801bb0b7  retn
0x1801bb0b8  lea     rax, aSignatureTypeF; "SIGNATURE_TYPE_FILENAME"
0x1801bb0bf  retn
0x1801bb0c0  sub     edx, 5Fh ; '_'
0x1801bb0c3  jz      short loc_1801BB131
0x1801bb0c5  sub     edx, 1
0x1801bb0c8  jz      short loc_1801BB129
0x1801bb0ca  sub     edx, 1
0x1801bb0cd  jz      short loc_1801BB121
0x1801bb0cf  sub     edx, 1
0x1801bb0d2  jz      short loc_1801BB119
0x1801bb0d4  sub     edx, 1
0x1801bb0d7  jz      short loc_1801BB111
0x1801bb0d9  sub     edx, 1
0x1801bb0dc  jz      short loc_1801BB109
0x1801bb0de  sub     edx, 3
0x1801bb0e1  jz      short loc_1801BB101
0x1801bb0e3  sub     edx, 2
0x1801bb0e6  jz      short loc_1801BB0F9
0x1801bb0e8  cmp     edx, 1
0x1801bb0eb  jnz     loc_1801BB7EE
0x1801bb0f1  lea     rax, aSignatureTypeR_1; "SIGNATURE_TYPE_REMOVAL_POLICY"
0x1801bb0f8  retn
0x1801bb0f9  lea     rax, aSignatureTypeL; "SIGNATURE_TYPE_LATENT_THREAT"
0x1801bb100  retn
0x1801bb101  lea     rax, aSignatureTypeS_1; "SIGNATURE_TYPE_STATIC"
0x1801bb108  retn
0x1801bb109  lea     rax, aSignatureTypeH; "SIGNATURE_TYPE_HOSTSENTRY"
0x1801bb110  retn
0x1801bb111  lea     rax, aSignatureTypeR_2; "SIGNATURE_TYPE_REGKEY"
0x1801bb118  retn
0x1801bb119  lea     rax, aSignatureTypeL_0; "SIGNATURE_TYPE_LOCALHASH"
0x1801bb120  retn
0x1801bb121  lea     rax, aSignatureTypeP_2; "SIGNATURE_TYPE_PEHSTR"
0x1801bb128  retn
0x1801bb129  lea     rax, aSignatureTypeF_0; "SIGNATURE_TYPE_FOLDERNAME"
0x1801bb130  retn
0x1801bb131  lea     rax, aSignatureTypeF_1; "SIGNATURE_TYPE_FILEPATH"
0x1801bb138  retn
0x1801bb139  lea     rax, aSignatureTypeW; "SIGNATURE_TYPE_WVT_EXCEPTION"
0x1801bb140  retn
0x1801bb141  mov     eax, 87h
0x1801bb146  cmp     edx, eax
0x1801bb148  ja      loc_1801BB278
0x1801bb14e  jz      loc_1801BB270
0x1801bb154  cmp     edx, 7Bh ; '{'
0x1801bb157  ja      loc_1801BB1F7
0x1801bb15d  jz      loc_1801BB1EF
0x1801bb163  cmp     edx, 75h ; 'u'
0x1801bb166  ja      short loc_1801BB1B7
0x1801bb168  jz      short loc_1801BB1AF
0x1801bb16a  sub     edx, 6Ch ; 'l'
0x1801bb16d  jz      short loc_1801BB1A7
0x1801bb16f  sub     edx, 4
0x1801bb172  jz      short loc_1801BB19F
0x1801bb174  sub     edx, 1
0x1801bb177  jz      short loc_1801BB197
0x1801bb179  sub     edx, 2
0x1801bb17c  jz      short loc_1801BB18F
0x1801bb17e  cmp     edx, 1
0x1801bb181  jnz     loc_1801BB7EE
0x1801bb187  lea     rax, aSignatureTypeD_1; "SIGNATURE_TYPE_DELTA_BLOB_RECINFO"
0x1801bb18e  retn
0x1801bb18f  lea     rax, aSignatureTypeD_2; "SIGNATURE_TYPE_DELTA_BLOB"
0x1801bb196  retn
0x1801bb197  lea     rax, aSignatureTypeA; "SIGNATURE_TYPE_ASEP_FILEPATH"
0x1801bb19e  retn
0x1801bb19f  lea     rax, aSignatureTypeT_3; "SIGNATURE_TYPE_TRUSTED_PUBLISHER"
0x1801bb1a6  retn
0x1801bb1a7  lea     rax, aSignatureTypeR_3; "SIGNATURE_TYPE_REVOKED_CERTIFICATE"
0x1801bb1ae  retn
0x1801bb1af  lea     rax, aSignatureTypeA_0; "SIGNATURE_TYPE_ASEP_FOLDERNAME"
0x1801bb1b6  retn
0x1801bb1b7  sub     edx, 77h ; 'w'
0x1801bb1ba  jz      short loc_1801BB1E7
0x1801bb1bc  sub     edx, 1
0x1801bb1bf  jz      short loc_1801BB1DF
0x1801bb1c1  sub     edx, 1
0x1801bb1c4  jz      short loc_1801BB1D7
0x1801bb1c6  cmp     edx, 1
0x1801bb1c9  jnz     loc_1801BB7EE
0x1801bb1cf  lea     rax, aSignatureTypeV_1; "SIGNATURE_TYPE_VERSIONCHECK"
0x1801bb1d6  retn
0x1801bb1d7  lea     rax, aSignatureTypeV_2; "SIGNATURE_TYPE_VDLL_X86"
0x1801bb1de  retn
0x1801bb1df  lea     rax, aSignatureTypeP_3; "SIGNATURE_TYPE_PEHSTR_EXT"
0x1801bb1e6  retn
0x1801bb1e7  lea     rax, aSignatureTypeP_4; "SIGNATURE_TYPE_PATTMATCH_V2"
0x1801bb1ee  retn
0x1801bb1ef  lea     rax, aSignatureTypeS_2; "SIGNATURE_TYPE_SAMPLE_REQUEST"
0x1801bb1f6  retn
0x1801bb1f7  sub     edx, 7Ch ; '|'
0x1801bb1fa  jz      short loc_1801BB268
0x1801bb1fc  sub     edx, 2
0x1801bb1ff  jz      short loc_1801BB260
0x1801bb201  sub     edx, 1
0x1801bb204  jz      short loc_1801BB258
0x1801bb206  sub     edx, 1
0x1801bb209  jz      short loc_1801BB250
0x1801bb20b  sub     edx, 1
0x1801bb20e  jz      short loc_1801BB248
0x1801bb210  sub     edx, 2
0x1801bb213  jz      short loc_1801BB240
0x1801bb215  sub     edx, 1
0x1801bb218  jz      short loc_1801BB238
0x1801bb21a  sub     edx, 1
0x1801bb21d  jz      short loc_1801BB230
0x1801bb21f  cmp     edx, 1
0x1801bb222  jnz     loc_1801BB7EE
0x1801bb228  lea     rax, aSignatureTypeP_5; "SIGNATURE_TYPE_PEMAIN_LOCATOR"
0x1801bb22f  retn
0x1801bb230  lea     rax, aSignatureTypeP_6; "SIGNATURE_TYPE_PEHSTR_EXT2"
0x1801bb237  retn
0x1801bb238  lea     rax, aSignatureTypeS_3; "SIGNATURE_TYPE_SIGFLAGS"
0x1801bb23f  retn
0x1801bb240  lea     rax, aSignatureTypeV_3; "SIGNATURE_TYPE_VFILE"
0x1801bb247  retn
0x1801bb248  lea     rax, aSignatureTypeD_3; "SIGNATURE_TYPE_DELTA_BLOB_ZSTD"
0x1801bb24f  retn
0x1801bb250  lea     rax, aSignatureTypeK_0; "SIGNATURE_TYPE_KCRCE"
0x1801bb257  retn
0x1801bb258  lea     rax, aSignatureTypeF_2; "SIGNATURE_TYPE_FOP"
0x1801bb25f  retn
0x1801bb260  lea     rax, aSignatureTypeS_4; "SIGNATURE_TYPE_SNID"
0x1801bb267  retn
0x1801bb268  lea     rax, aSignatureTypeV_4; "SIGNATURE_TYPE_VDLL_X64"
0x1801bb26f  retn
0x1801bb270  lea     rax, aSignatureTypeP_7; "SIGNATURE_TYPE_PESTATIC"
0x1801bb277  retn
0x1801bb278  mov     eax, 91h
0x1801bb27d  cmp     edx, eax
0x1801bb27f  ja      loc_1801BB30B
0x1801bb285  jz      short loc_1801BB303
0x1801bb287  sub     edx, 88h
0x1801bb28d  jz      short loc_1801BB2FB
0x1801bb28f  sub     edx, 1
0x1801bb292  jz      short loc_1801BB2F3
0x1801bb294  sub     edx, 1
0x1801bb297  jz      short loc_1801BB2EB
0x1801bb299  sub     edx, 1
0x1801bb29c  jz      short loc_1801BB2E3
0x1801bb29e  sub     edx, 1
0x1801bb2a1  jz      short loc_1801BB2DB
0x1801bb2a3  sub     edx, 1
0x1801bb2a6  jz      short loc_1801BB2D3
0x1801bb2a8  sub     edx, 1
0x1801bb2ab  jz      short loc_1801BB2CB
0x1801bb2ad  sub     edx, 1
0x1801bb2b0  jz      short loc_1801BB2C3
0x1801bb2b2  cmp     edx, 1
0x1801bb2b5  jnz     loc_1801BB7EE
0x1801bb2bb  lea     rax, aSignatureTypeT_4; "SIGNATURE_TYPE_TARGET_SCRIPT_PCODE"
0x1801bb2c2  retn
0x1801bb2c3  lea     rax, aSignatureTypeM_2; "SIGNATURE_TYPE_MACROHSTR_EXT"
0x1801bb2ca  retn
0x1801bb2cb  lea     rax, aSignatureTypeD_4; "SIGNATURE_TYPE_DOSHSTR_EXT"
0x1801bb2d2  retn
0x1801bb2d3  lea     rax, aSignatureTypeM_3; "SIGNATURE_TYPE_MACHOHSTR_EXT"
0x1801bb2da  retn
0x1801bb2db  lea     rax, aSignatureTypeE; "SIGNATURE_TYPE_ELFHSTR_EXT"
0x1801bb2e2  retn
0x1801bb2e3  lea     rax, aSignatureTypeI; "SIGNATURE_TYPE_IL_PATTERN"
0x1801bb2ea  retn
0x1801bb2eb  lea     rax, aSignatureTypeP_8; "SIGNATURE_TYPE_PEPCODE"
0x1801bb2f2  retn
0x1801bb2f3  lea     rax, aSignatureTypeF_3; "SIGNATURE_TYPE_FOPEX"
0x1801bb2fa  retn
  ... truncated ...
```
